Webapp-Deployment
=================

This is an ansible playbook for deploying https://github.com/squidboylan/webapp
in a scalable way. It deploys it with 1 haproxy node, 1 mysql node, and 1+ app
nodes.

In order to run the playbook, copy vars/example.yml to vars/prod.yml. Configure
the vars/prod.yml file as described in the file. Then run the playbook with:
``ansible-playbook site.yml -e "env=prod"``.

Because this playbook creates the app nodes and mysql nodes on the private
network, it is best run from a host on the same network, or with a jump host
speicified in the group_vars dir for the database_servers and app_servers
groups. Without a jump host, a computer outside of
the private network will not be able to reach the servers on the private
network.
