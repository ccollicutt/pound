Pound
=====

This Ansible role enables users to install and configure the pound reverse proxy, load balancer and HTTPS front-end for Web server(s)

Requirements
------------

This role requires Ansible 1.4 or higher, and platform requirements are listed
in the metadata file.

Role Variables
--------------

The variables that can be passed to this role and a brief description about
them are as follows. See the Pound configuration documentation for details:

```
pound_svc_name: pound

# What level to log at
log_level: 1

# What ip address should pound listen on?
listen_http_address: 127.0.0.1

# What port should pound listen on?
listen_http_port: 80

# What ip will pound be proxying traffic to?
# - add more by adding additional items in the form ['ip', 'port']
backend_servers: 
  - [ '127.0.0.1', '8080' ]
  - [ '192.168.100.100', '8080']
```

Examples
--------

1) Install pound and set the default settings.

	- hosts: all
	  roles:
	    - role: pound

Dependencies
------------

To install Pound in RedHat derivatives you will need the EPEL repository.

License
-------

BSD

Author Information
------------------

curtis@serverascode.com

Thanks
------

This was based on the [NTP module](https://github.com/bennojoy/ntp).
