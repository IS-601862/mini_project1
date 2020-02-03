# Git basic commands and description

## Repository 

Repository is the storage location or place where your work is stored when you do some work.
### Example: 
when you do some work, you either store it in your local storage device like hard drive in PC or thumb drive or publish on site which is stored in cloud to share. Git also has local and public location to store work, and its called repository.

## Clone

Clone as it sounds, is the copy of your local commit or local work, commonly used to share your local work to public/remote repository. 
To use this command simply type "git clone" and it will make copy of your local work.
    
    git clone <url from github>

### Example:
When you upload your music file from computer to either cloud or your phone device, you are uploading a copy of your file. It is not realtime file it-self, it is copy, so once you upload the file and then make change to it in your local computer it will not change **"clone"** file in remote, becuase it is not actual file it-self but its copy. 

## Frok

Fork is similar to Clone, however it is to test or experiment on remote repository (github) rather then local, where peopel can share and edit files to collaborate.
To do fork, you use the git clone command with your github link, which allows you to share your clone or in this case, fork on remote repository rather then your local. 
### Example:
A google drive document is perfect example for fork. Local word file works like clone, while google drive file works like fork, where it is stored remotely and all the members has access to it and can edit it. 

## Branch

Branches are basically pointers showing what is involved in your current work, or what are the parent commit of your current commit. 
To branch, the command is "git brnach NAME-OF-BRANCH". Include what you want to name the branch instead of "NAME-OF-BRANCH".

    git branch new_branch

### Example:
If a food item such as Cake has multiple steps, branches simply shows what have been done before or what work was related to get to point where you are not. For example, before putting cake in oven, you added eggs, flour, and coco; so each item is a commit and there would be arrow showing step by step whats added, which is branching.

## Commit
Commit is basically the work done in git. Any work you do in git is known as git commit. It is stored in the repository. 
to commit, simply use the command 

    git commit -m "Put your additional instructions here"

### Example:
any work you do, can be sensed by others. Git commit is simply for repository to know you did the work so it can store it, which other can see.

## Merge 
As it sounds, merge is mixing two commits or work into one work. In git language, two or more parent commints, branching into one. 
To use merge, simply select (checkout** will go over soon) one commit, and type command **"git merge OTHER-COMMIT-NAME"**, where OTHER-COMMIT-NAME is the other commit you want to merge your currently selected commit.

    git merge "Other Commit Name to merge with" 

### Example: 
If you want to make chocolate milk, either select coco or milk, in this case lets do milk and simly do "git merge coco" and now you have chocolate milk, which has branches (parent commits) from coco and milk commits.   

## Checkout
Checkout in git is what 'Select' is for everything else. Basically, if you checkout a commit, that means you have selected that commit or currently working on that commit. 
To use checkout, type command 

    git checkout NAME

add the NAME of the commit wish to select or checkout. There are other shortcut commands that can be performed with checkout, which can be introduced at later level.

### Example: 
from our previous example of chocolate milk, if you want to add coco in to the milk rather then milk in to coco, do 

    git checkout coco".

Now you have coco in your hand, or its selected, and you can do 

    git merge milk

because you already have selected coco and just need to tell it what to merge it with.

## Push

Push is normal computer language is uploading or publishing. Since we already talk about cloning and remote repository for sharing work, Push does the uploading your work from your local repository to remote repository so others can access your updated commit or work.
To use push, simply use command 

```git    
git push
```

### Example: 
When you have local word file, no one in remote site has access to it. However, when you upload it on some cloud system like google drive, others with access or your self from remote location can access. This process of uploading a local file is what push does. 

## Pull
If push is uploading, what you think pull means? Exactly! Pull in git is what downloading is in normal computer terms. Pull means to download or retrieve "pushed" files from remote repository to local repository, so you can have access to it on your local repository. There is another command called "fetch", which also does what downloading does, however the main difference between fetch and pull is that, fetch only download files, while pull not only downloads it but also opens and merge (update) with your work so you get start working from the point left off by "pusher".
To use pull, just use command 

    git pull 
    
Example: if you are on stage 2 of some process and someone else "pushed" file with level 5, when you use "git pull", the system will download that file and also merge it with your system, so its updated to level 5 so you can work from there and on. 

## Remote add / remove / show 
**"git remote add NAME"** adds your local repository or storage to remote repository. So it is like uploading a folder online, which also takes all the files or in git language, all the commits in the repository with it. 
**"git remote rm NAME"** does exactly opposite of adding, it removes a named repository. However, it does not remove name repository from remote repository, it actually removes the route to that specific repository from your local repository. Confusing right? Well, in simple words, if you download a file and then delete it, you have simply removed it from your computer and not from the internet. Same way, "remote remove" removes route to the named repository from your local repository and not from remote source. 

```git
git remote show NAME
```

shows you the link or route where the repository was retrieved or could be retrieved from. It is basically a website address or route address to specified repository/location.
