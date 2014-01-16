dokku-pre-release-command
=========================

A plugin for [Dokku](https://github.com/progrium/dokku) that allows you to
run arbitrary commands inside an app container after deploy.


Installation
------------

    cd /var/lib/dokku/plugins
    sudo git clone https://github.com/philippbosch/dokku-pre-release-command.git pre-release-command


Usage
-----

In your application's folder `/home/dokku/app_name` create a file called
`PRE_RELEASE_COMMAND` that includes a bash command (or multiple joined with
`&&`) that shall be run inside the app container on each deploy right before
the release step.


Examples
--------

Say you need a specific Ubuntu package but don't want to create a custom
buildpack. For example, I needed [OpenSCAD](http://openscad.org/) for an app
of mine. This is what I put in the `PRE_RELEASE_COMMAND` file:

    apt-get update &&
    apt-get install -y software-properties-common &&
    add-apt-repository -y ppa:chrysn/openscad &&
    apt-get update &&
    apt-get install -y openscad


License
-------

[MIT](http://philippbosch.mit-license.org/)
