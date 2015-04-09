WWU DevOps Site Source Code
========================

#How to get it#
###Installing Ruby###
To build and view the source code you have to have Ruby installed (we recommend [rbenv](https://github.com/sstephenson/rbenv)). 
###Installing dependencies###

```bash
 ~$: gem install bundle 
 ~$: bundle install
```

###Cloning branches###
Clone the source branch (this one) with 

```bash
git clone https://github.com/wwudevops/wwudevops.github.io --branch source --single-branch
```

The master branch is actually where all the built files go so GitHub is able to host the site for us, so clone that one to the build directory of the repository you just cloned.

```bash
~$: cd wwudevops.github.io
~$: git clone -b master https://github.com/wwudevops/wwudevops.github.io build
```

The site is built with the static site generator [Middleman](http://middlemanapp.com/).

#How to edit it#
Layouts for the site are written in haml and posts should be done in markdown. To create a new post make a file named {year}-{month}-{day}-{post-name}.html.md (e.g. 2014-11-10-first-post.html).

#How to preview changes#
To preview changes you should run the Middleman server on localhost:4567  with the command ```middleman server```. Depending on your Ruby configuration, it may complain about some dependency conficts in which case it can be started with ```bundle exec middleman server```.

#How to build changes#
Changes can be built with ```middleman build``` (or ```bundle exec middleman build```). This will update the files in the cloned build directory with your latest changes. For those changes to take effect, they have to be committed and pushed up to the remote.

```bash
~$: cd build
~$: git status  # check before you commit
~$: git add .
~$: git commit
```
