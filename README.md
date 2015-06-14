# Vagrantfile for a Jekyll provider

This file installs Jekyll on a ubuntu trusty box. After that a test site is 
generated at the Vagrantfile directory and the jekyll server is startet at this directory.

This jekyll installation is using Ruby 2.2.1. and using RMV to install it.

# How to use

The standard configuration forwards port 8082. Therefore *http://localhost:8082* starts the test site.
Vagrant starts Jekyll as a backround service.

To start jekyll manually start within the directory you edit your jekyll site:

~~~bash
jekyll serve -P 8082 -H 0.0.0.0
~~~

To change to the forwarded port one has to edit *Vagrantfile*.
