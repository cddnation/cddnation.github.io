---
layout: page
title: Git
group: "navigation"
---

This is the Git branching strategy used at CDD.

# Index

* Git
    * Introduction
    * Git branches
    * Deployment strategy
* Useful commands
    - ... 

## Perch Deployment Strategy

### Local setup

Firstly, clone the repo.

The web root needs to be set to app/

Pull the latest app/resources/ folder from the live/staging server, depending on which is available.

Run:

    $ sudo npm install
    $ sudo bower install
    $ gulp watch

### Staging & Production

Locally run the following to get the latest dist, and commit it to production:

    $ gulp

On the staging/production server make the site directory and change to it:

    $ mkdir {projectname}
    $ cd {projectname}

Initialize the repo and enable sparse checkouts.

    $ git init
    $ git config core.sparsecheckout true

Specify the directories wanted:

    $ echo dist/ >> .git/info/sparse-checkout

Add the remote:

    $ git remote add -f origin git@codebasehq.com:cdd-development/{projectname}/{reponame}.git

Fetch the files:

    $ git checkout {branch}
    $ git pull origin {branch}

(staging or production):

Pull the latest resources/  or any other user generated content folder from the staging/production server, depending on which is available, and put the contents of this into dist/perch/resources. You can use the rsync command for this.

The web root needs to be set to dist/ if you are using gulp for your project.

Set permissions of files and folders on the server.
