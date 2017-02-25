---
layout: post
title:  "When git clone tries to be annoying saying Permission Denied!"
date:   2017-02-25 11:49:45 +0200
categories: Weblog Post
---
# How to generate ssh and introduce it to your github account:
Once you are getting Permission Denied message from git these steps are what you need to do:
- ssh -T git@github.com
It will tell you one more time that you are successfully authenticated or you do not have proper permission.
- ls -al ~/.ssh
you can see all keys relative to you

- move to the users/your name/.ssh folder
- ssh-keygen -t rsa -b 4096 -C "XXX@gmail.com"
generate a new key for your account which is connected to github
- eval "$(ssh-agent-s)"
tell you the agent number

- ssh-add -K ~/.ssh/id_rsa
it will ask you to enter a pass phrase then adds Identity to ~/.ssh/id_rsa 

- pbcopy < ~/.ssh/id_rsa.pub
copy the content of your rsa key to the clipboard

- Open your github setting from github site and create a new ssh key and paste the content to the new key

 -  ssh -T git@github.com
 just to make sure you are successfully authenticated

 - Now if you go to the github setting in the website you will see that the recently created key is activated


[Github Docs]:https://help.github.com/articles/connecting-to-github-with-ssh/