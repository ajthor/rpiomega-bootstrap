Raspberry Pi Omega Ansible Configuration Playbook
=================================================

Usage:
------

Run the following command to bootstrap a node in the cluster.
The following variables must be defined by you in the `--extra-vars` argument on
the command line:

- `ip_address`: the static IP address you wish to assign to the node.
- `hostname`: the hostname you want the node to be identified by.
- `type`:
  - `master`: set the current node up as the master node.
  - `node`: set the current node up as just another node in the cluster.

To set up the master node:

    ansible-playbook site.yml -i "< current IP address >," --extra-vars "ip_address=< target static IP address> hostname=rpiomega-master type=master"

Make sure to add `--check --diff` to see changes before you commit them.

To set up the minion nodes:

    ansible-playbook site.yml -i "< current IP address >," --extra-vars "ip_address=< target static IP address> hostname=rpiomega-node-1 type=node"
