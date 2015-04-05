# git + lab = gitlab

[![Build Status](https://travis-ci.org/numa08/git-gitlab.svg?branch=travis.ci)](https://travis-ci.org/numa08/git-gitlab)

lab is a command line tool that wrap `git` in order to extend it with extra features and commands that make working with GitLab easier.


~~~sh
$ git lab clone numa08/dejiko

# extends to:
$ git clone git://${gitlab.url}/numa08/dejiko.git
~~~

## Installation

TODO

## Configure

Set the value of Gitlab-url and token.

~~~sh
$ git config --global gitlab.url http://gitlab.example.com

$ git config --global gitlab.token GITLAB_SECRET_TOKEN
~~~

then, set gitlab namespace and project.

~~~sh
$ git config gitlab.project [NAMESPACE]/[PROJECT]
~~~

## Commands

### git clone

~~~sh
$ git lab clone numa08/dejiko
> git clone git://{gitlab.url}/numa08/dejiko

$ git lab clone -p numa08/dejiko
> git clone git@{gitlab.url}/:numa08/dejiko
~~~

### merge request

~~~sh
$ git lab merge-request -b basebranch -h headbranch
>open text editor to edit title and body
>open pull request on GitLab

$ git merge-request -b forked:branch -h origin:branch -m "Fix issue #xxx"
~~~

### git merge

~~~sh
$ git lab merge [MERGE_REQUEST_ID]
~~~

### git show

~~~sh
$ git lab show -- issue/10
> open http://gitlab.example.com/NAMESPACE/PROJECT/issues/10
~~~