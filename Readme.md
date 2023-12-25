# Kubernetes Cluster Installation and Initialization with Ansible

## This guide outlines the steps to install and initialize a Kubernetes cluster on Ubuntu using Ansible.
## Prerequisites

Ubuntu machines to serve as master and worker nodes.
Ansible installed on your local machine.
SSH access to the target machines with sudo privileges.
Basic knowledge of Ansible and Kubernetes.

## Here are the steps to configure SSH key access to the nodes:

### Generate SSH Key Pair:
On your local machine, generate an SSH key pair (public and private key) if you haven't already done so:
shell

    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

Choose a secure passphrase when prompted or leave it blank for convenience.
This command will generate two files: id_rsa (private key) and id_rsa.pub (public key).

### Distribute Public Key:

Copy the public key (id_rsa.pub) to the target nodes that you want to access:
shell

    ssh-copy-id user@node-ip

Enter the password for the user account on the target node.
This command will append the public key to the ~/.ssh/authorized_keys file on the target node, allowing SSH key-based authentication.

### Test SSH Access:

Verify that you can now access the target node without entering a password:
shell

    ssh user@node-ip

You should be able to log in to the node without being prompted for a password.
