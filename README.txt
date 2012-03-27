piwik-buildout
==============

This is a buildout to set up a piwik installation.

It is likely that you have to install some dev packages on your server in
order to compile MySQL, PHP and Nginx. Have a look to the configure-options in
the buildout sections to evaluate the ones you may have to install.

The following will be installed::
- MySQL
- PHP
- Nginx
- Piwik

In buildout.cfg is a section called globals where the user and port for nginx
can be set. The nginx is not considered to be the only webserver for the server, 
so the port where it will be running is set to 9090 by default. Have a look to
the globals section in the buildout.cfg

The user of mysql installed with zest.recipe.mysql defaults to root. You
should set a new password for the user after running the buildout and *before*
set up piwik with ’./bin/mysqladmin -u root password’.


Usage
-----
- checkout the repository
- set the appropriate user, group, ports and hosts in the section globals
- bootstrap and run buildout
- start everything with ’./bin/piwik_control start’
- point your browser to http://[hostname]:[nginx-port] and set up piwik


todo
----
- enhance zest.recipe.mysql to set a different port for the MySQL Server
- extend documentation
- test, test, test
