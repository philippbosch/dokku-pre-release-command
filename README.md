dokku-pre-release-script
========================

A plugin for [Dokku](https://github.com/progrium/dokku) that allows you to 
run arbitrary commands inside an app container after deploy.


Installation
------------

    cd /var/lib/dokku/plugins
    sudo git clone https://github.com/philippbosch/dokku-pre-release-script.git pre-release-script
    dokku plugins-install


Usage
-----

In your application's folder `/home/dokku/app_name` create a file called 
`PRE_RELEASE_SCRIPT` that includes a bash command (or multiple joined with 
`&&`) that shall be run inside the app container on each deploy right before
the release step.


License
-------

[MIT](http://philippbosch.mit-license.org/)
