# Monitoring pluging Haproxy python

This plugin allows you to monitor your HAproxy loadbalancer. You can see the state of your frontend (servers loadbalanced) and backend (HAproxy itself)

### Requirements

- New relic account, find our plugin in the plugin central
- Python 2.7 with the python lib requests installed ( pip install requests // find the library directly into the OS's official repository // build it from the sources : http://www.python-requests.org/)
  - Reports of it working on Python 2.6.6, however your mileage may vary and this is not supported.

### Installation

Create the newrelic conf directory if it is not created yet

`mkdir /etc/newrelic`

Copy the config file into this directory

`sudo cp agent-a0labs.cfg /etc/newrelic/`

The python `requests` library is required:

`pip install requests`

If you chose to use a virtualenv, you may need to modify the example upstart/daemon scripts.



Fill the informations in the cfg file:
- License Key
- URL to access the stat CSV Haproxy's file
- user and password
Optional:
- enable/disable logs and specify the directory

### Daemonize
There are a few ways to be sure the plugin remains running as a Daemon or service, some are better than others - but each should be selected based on your need.

- use a nohup to launch it in background an detach it when you'll quit the terminal
- use a crontab like "@reboot /usr/bin/python /path/to/bin"
- put it in your /etc/init.d
- use upstart

./daemonize has some examples, you should read their comments before trying to use the scripts


### Support

Please useG [Github issues](https://github.com/Etherhypnos/agent-haproxy-a0labs/issues) for support.