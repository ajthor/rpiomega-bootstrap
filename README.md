Raspberry Pi Omega Ansible Bootstrap Playbook
=============================================

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

What is Raspberry Pi Omega? 
---------------------------

In set notation, Omega is the greek letter used to represent the Universal Set, and is also used to represent the first number after infinity. Raspberry Pi Omega is a cluster computing platform using the credit-card sized SBC, Raspberry Pi. It is designed as an educational and personal tool for software development, and is designed to work as a set, hence the name.

Raspberry Pi Omega is developed as a platform for performing development and computing tasks on a self-hosted cluster of Raspberry Pi's. It is designed to be an inexpensive, educational entry-point into cluster computing, utilizing technologies such as Configuration Management, Container-Based Virtualization, and Continuous Integration.

Though the system can run with a single node, it is better to use at least 3 nodes With enough Raspberry Pi's, the system can become quite powerful.

See more in the rpiomega repository.
