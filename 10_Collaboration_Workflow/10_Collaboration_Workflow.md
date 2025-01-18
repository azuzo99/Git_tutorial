# Collaboration Workflow

## Why not single branch?

Assume we have 3 collaborators:

* Forrest
* Pamela
* David

Everyone is cloning repository `master` branch and start to work.

Forrest is making changes and pushes the code to Github what is perfectly fine

![alt-text](./screenshots/image_10_01.png)

After that Pamela is trying to push her changes. but she faces a problem, because `master` is ahead

![alt-text](./screenshots/image_10_06.png)

She has to pull the changes and merge into her branch

![alt-text](./screenshots/image_10_02.png)

Then she is able to push the changes

![alt-text](./screenshots/image_10_03.png)

Meanwhile David is working on his branch, but suppose he is working on the feature that has a bug. He has a problem with the push too, so needs to reproduce steps that Pamela did. So he pulls from `master`

![alt-text](./screenshots/image_10_04.png)

Now he can push, but the problem is that if he needs to discuss the bug with others he has to push it. That means on the `master` we have the bug, so our app/infra is not working properly, till the bug won't be resolved

![alt-text](./screenshots/image_10_05.png)

To avoid this **Feature branches** have been invented

## Feature branch

According to our example with Forrest, Pamela and David. Workflow with feature branches has been totally different as changes made by each of those developers will be separated into different branches.

David starts `add-dark-theme` branch from master and wants Pamela to review his changes

![alt-text](./screenshots/image_10_07.png)

Pamela is working on her own branch `animated-scroll`, but if needed she can easily switch and pull feature branch `add-dark-theme` to review work from David. **Branches are still separated**

![alt-text](./screenshots/image_10_08.png)

Next day David is coming back to work and he still can work on his branch adding new features. After a changes he pushes code to Github and creates `Pull Request`, after which acceptance, changes are merged to `master`.

![alt-text](./screenshots/image_10_09.png)

## `git merge`

We do not always need to create `Pull Request` to merge branches. We can use `git merge <branch>` command to do it.

***Warning:*** You need to be aware where you are merging. If you want branch `feature` to be merged into `master`, you have to be on `master` and invoke `git merge feature`.

## Pull Request

Pull Requests are native feature for Github, not Git. They allow to review changes by developers before they will be merged into the branch. Pull Request is the last stage before merging changes. In most of the corporate repositories direct `git merge` command to `master/main` is blocked and can be done **only after accepted Pull Request**

![alt-text](./screenshots/image_10_10.png)

## Branch Protection Rules

Branch Protection Rules is the feature that blocks direct merge mentioned above. We can configure branches in Github to increase the security and reduce conflicts cases.

![alt-text](./screenshots/image_10_11.png)

![alt-text](./screenshots/image_10_12.png)

## Forking

Fork & Clone is the popular workflow that is used widely in open-source projects. Image situation where we have a Spark official repository. Fork & Clone give us opportunity to create a personal copy of repository on our own Github and work on it. While copying our repository and contribute to this we are maintaining new versions of features that will be pushed into original repository after pull request accepted by group of maintainers of official repository.

### How to fork?

Let's try to fork official repository of `Apache/Spark`.

1. We are going to the official repository of Apache Spark and click the `fork` button
    ![alt-text](./screenshots/image_10_13.png)

2. We need to name our forked repo
    ![alt-text](./screenshots/image_10_14.png)

3. Our forked repository copy is created
    ![alt-text](./screenshots/image_10_15.png)

4. We can copy it to our local directory and contribute
    ![alt-text](./screenshots/image_10_16.png)

### How does it work under the hood?

Basically many developer's repositories can exists

![alt-text](./screenshots/image_10_17.png)

Every developer has its own forked repository

![alt-text](./screenshots/image_10_18.png)

When repository is forked and cloned `origin` is set to our forked repository and `upstream` is set to official repository

![alt-text](./screenshots/image_10_19.png)

Due to this mechanism our changes can be pushed only via our forked repository and changes can be done only by Pull Request (origin capabilities)

![alt-text](./screenshots/image_10_20.png)

But pull can be done directly from official repository (upstream capabilities)

![alt-text](./screenshots/image_10_21.png)

Overall flow can be found below

![alt-text](./screenshots/image_10_22.png)
