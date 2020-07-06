## first open those file which you want to upload on githhub
then enter step by step

                git init
                git add .
                git commit -m "what ever you want to write"
                git push
## firstcreate a reposetry then you get (git remote add origin https://github.com/prince21298/JAVASCRIPT.git) like this code 
then do it

                git push -u origin master

## one way more to upload your file on github if have clone file

                git status
                git init
                git add .
                git commit
                git push -u origin master

## To  verify you on github through terminal

                git config --global user.email my_Id@gamil.com
                git config --global user.name userName



if we want to Delete the git in it file then run 

                rm -rf .git
if we want to check the status then run

                git status
if we want to choose 1 file from the File system then run 
                git add "your file name"/
when we want to pull the data then type

                git pull
if we want to see the data inside our file then run
                ls


## GITHUB COLABREATOR
First you have go to your repo then open your setting after that you have to go in manage-acess then you have to give your
your github password. then manage-acess will open after that you can send invation link to appropriate person whom you want 
to colabrate after he will accept your invation then he will also able to acess your Repo.


## LIVE PROJECT ON GITHUB
first you have to clone your file from github through your VS CODE
then you have to open that direcotory in VS CODE then you have to changewhatever you want if you want to make directory than
you can make that  one also. if you want to do anything then you can.
after you have to commit from Source control for that you have to press 

                ctrl+Shift+G
after that you have to give comment then you have to cllick to right sign.
then after you have to use extennsion to push or pull code from github.
first you have to open search bar for that you will 

                ctrl+Shift+P

## For Push
then you have to search "git Push" when you will click to git push after that you have to verify
for verifying you vs code open will search-bar in this first you have to put your github-id name
after this vs code will open again search bar for password then you have to put your github password


## Git Pull
then you have to search `git Pull` when you will click to git pull 
after clicking git pull you will get all updates in from github in your local clone for this you dont need to verify yourself.


# GIT AUTHOENTICATION
## There is a two way for Authentication
## 1, with Local
## 2, With SSH_KEY


### 1, Through Local 
for local there is a four command.
    
    git config --global user.name "prince21298"
    git config --global user.email "MY_NAME@example.com"
    git config --global user.password "your password"
    git config --global credential.helper cache
    git config --global credential.helper 'cache --timeout=3600'

#### I got that Code from this [link](https://help.github.com/en/github/using-git/caching-your-github-password-in-git#platform-linux)

But in this you will be able your code-changes but for some time not for all time and there is also some thing like you have
to run these four code in appropriate file.
like first you have to open your terminal and after that you will open that file where you clone your repo then you will run 
these four command.
its only for time limitation.

### 2,  Through SSH_KEY
for local there is a four command.

        ssh-keygen -t rsa -b 4096 -C "your email id which is login on github"
after enter this you have to give your file name like i gave .SSH_KEY
then run this you will get id.

        eval "$(ssh-agent -s)"
after run this command for add SSH KEY in .SSH_KEY file.

        ssh-add ~/"your file name which you gave after putting first command"
then after run this command

        cat "your file name which you gave after putting first command".pub
then you will get SSH public key that you have to store in your github SSH key



YOU ALSO CAN USE THESE COMMAND

    ssh-keygen -t rsa -b 4096 -C "your email id in string which is login on github"
    ssh-add ~/"your file name which you gave after putting first command"
    cat .SSH_KEY.pub



SSH KEY in Github
must look at this two link.
#### [link1](https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
#### [link2](https://zzpanqing.github.io/2017/02/28/github-push-without-username-and-password.html)

for Github SSH key first you have to open your setting then there you will get `SSH and GPG keys` which you have to click
then you will get option add for "New SSH key" youhave to click it.
after that you will get
Tittle
KEY
In tittle you have to write tittle. you can write whatever you want.
In KEY you have to write that key which you got in terminal by the run of last command.

while cloning you have to remember some things
like 
when you will clone repo then clone with SSH link not with HTTPS link.
For SSH link when you will go to link go to frst on repo then click "clone or Download" then you get link but it will be 
https link which you have to be change in SSH link. For that you you have to click "Use SSH" you will get it in corner after
clicking on "clone or Download". then copy that SSH link.
then simply clone in your local directory.
then you can use easily
to push 
to pull
without username and password.


# If i am getting this type of PUBLIC_KEY permission denied error so what we have done ---
you have run this command---

        eval "$(ssh-agent -s)" 

output will come -- generate pid number
and then run this commamd---

        cat ssh_key.pub

you have get one public_key id and then you have to setting--> ssh_key-->add ssh_key.


## Merge conflict on Github
To resolve by the command line...

## linux
(1) Open the terminal
(2) Navigate your existing repo that has Merge conflict.

        cd /repo
(3) check the git status

        git status
(4) and Open your vsc(visual studio code)

        vsc code
(5) To see your begining file you got your conflict file. will see like that.
       


(6) Remove all these confliction and white space from your code and then save all those file which have conflict issue
(7) Add or stage your changes

        git add .
(8) commit changes with your comment

        git commit -m "resove the conflict issues!"
