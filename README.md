# git_ssh_sollution
a easy way to connect your pc over ssh to your github account

#############################################################

# setting up the ssh key :

1. checking if there is any ssh key already connected to your PC :


ls -al ~/.ssh
(# Lists the files in your .ssh directory, if they exist. if exists then go to the number 4)

________________________________________________________________

2 .generating a new ssh key :


$ ssh-keygen -t ed25519 -C "your_email@example.com"

or ,

$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

________________________________________________________________


3.adding the new key to  your PC :

eval "$(ssh-agent -s)"
$ ssh-add ~/.ssh/id_ed25519
or ssh-add ~/.ssh/id_rsa

after running this command you can run echo $

________________________________________________________________

4. adding a key to your github :

$ clip < ~/.ssh/id_ed25519.pub

(#paste it in the box)

________________________________________________________________


5 .testing the ssh connection :
$ ssh -vT git@github.com

__________________________________________________________________

list all the keys added to your ssh agent -

eval "$(ssh-agent -s)"
ssh-add -l


