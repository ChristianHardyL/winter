# WINTER

## Phase 1

over as of now

## Phase 2

the focus of this page - building and documenting new network. in align with key tasks: installing set of virtual machines from scratch, connecting those machines to multiple sub-nets, installing and configuring services, and writing guides to follow my decision-making process.

### 0 - write a guide --> you're looking at it

### 1 - build the following machines

build the following:

* Ubuntu 18.04
* CentOS Stream
* Alpine
* pfSense 2.4.4 (no Guest Additions necessary)
* Windows 10
* *Ubuntu 12.04*
* *CentOS 5*

### 2 - set up an internal (host-only) network for machines 1-3

### *3 - set up a second internal network for machines 5-6*

### 4 - connect all machines to the internet by routing through machine 4 (pfSense)

use the pfSense machine's DHCP server to provide each other machine a reserved internal IP address.

### 5 - install and configure the nginx HTTP server on your alpine machine

1. it doesnt matter what web pages you decide to host but put up something other than the default page.
2. set up the pfSense machine to pass external connections on port 80 to your web server

### 6 - install and configure the unbound DNS server on your CentOS Stream machine

1. Set up a DNS zone that is <handle>.c3t --- for instance, neon.c3t.
2. Set up your DNS to provide the external (bridged) address of your pfSense machine when asked for your zone.
3. Set up recursive DNS lookups.
4. Set your pfSense machine to use your new DNS server as its DNS source, and set its DHCP server to provide your new DNS server's address as the default DNS server.

### 7 - install and configure OSSEC in "Server" mode on your ubuntu 18.04 machine

1. *install in Agent mode on alpine and centos stream machines, and connect the agents to OSSEC server*

### *8 - install and configure gogs on centos 5 machine*

*set up nginx server as a reverse proxy for gogs on the /git/ folder (alpine)*

### *9 - set up a full email server on your ubuntu 12.04 machines*

1. install postfix as an SMTP server
2. install dovecot as an IMAP/POP3 server
3. install koushin as a webmail server

    set up nginx server on alpine as a reverse proxy for koushin on the /mail/ folder

4. add DNS records to properly resolve your web server

## Phase 3

coming soon
