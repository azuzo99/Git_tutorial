# Workflow

The entire Git workflow includes 3 stages

![alt text](./screenshots/image_02_01.png)

## **Work on stuff**
Where we are making changes, adding/deleting/changins stuff in local working directory. 

In this stage changes are not tracked yet, so they are only developed locally beyond the changes stage

![alt text](./screenshots/image_02_03.png)


## **Staging Area** 
Where we are grouping stuff for specific changes. We are switching to this stage using `git add` command.

![alt text](./screenshots/image_02_02.png)

For example we can group highlighted changes into one adding them 1 by 1. Then in the staging area you can prepare them for commit.


## **Commit**

Commit is not the same as saving something. It is more like doing a checkpoint in the project. You can group the changes and commit them together as the mark in the history. This change should be precisely described to make changes and updates clear

You can commit your changes groups using `git commit -m "Your message"`