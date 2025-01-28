# Git Under The Hood

## `.git` file

`.git` file includes necessary stuff that allows the Git system operates behind the scenes

![alt-text](./screenshots/image_14_01.png)

we can navigate there using

```bash
ls -a
cd .git 
```

![alt-text](./screenshots/image_14_02.png)

### refs

`refs` directory contains the information about `heads`, `remotes` and `tags`

![alt-text](./screenshots/image_14_03.png)

For example in `head` we have information about where the head fo given branch is located

![alt-text](./screenshots/image_14_04.png)

Same for `remotes` and `tags`
![alt-text](./screenshots/image_14_05.png)
![alt-text](./screenshots/image_14_06.png)

### HEAD

Git HEAD folder contains the hash that refers to the commit that the HEAD is attached to for a current branch

![alt-text](./screenshots/image_14_07.png)

### objects

This folder contains all repo files. This is were backups sit, commits , files and more. Files are always compressed and encrypted.

![alt-text](./screenshots/image_14_08.png)

Git is using SHA-1 algorithm to create hashes

There are 4 types of objects in Git:

* BLOBs
* Trees
* Commits
* annotated tags

![alt-text](./screenshots/image_14_09.png)

Git is key-value database that keeps organized rows distinguished by unique keys that are used to retrieve objects (hashes).

Objects in Git are organized into the hierarchy where hashes refers to certain parent tree of commit

![alt-text](./screenshots/image_14_15.png)

#### BLOBS

![alt-text](./screenshots/image_14_10.png)

Are the most basic organization units of Git. They keep the content of files. They do not even store names, this is pure content of files distinguished by hash

#### Trees

![alt-text](./screenshots/image_14_11.png)

Trees store the contents of the directory. Each tree contain a pointer to another tree of blob and filename

![alt-text](./screenshots/image_14_12.png)

#### Commits

![alt-text](./screenshots/image_14_13.png)

Commits combine tree along the information chain of changes. Commits store reference to the parent commit, author, committer and commit message
