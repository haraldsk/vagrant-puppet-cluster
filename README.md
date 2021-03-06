Vagrant puppet cluster  - easily set up clusters in vagrant.
==============
# Prerequisits for install
 
  * Make sure you have vagrant http://vagrantup.com/

# Install

 From git root 
  * git submodule init && git submodule update
  * edit conf/cluster.yaml 
  * rake generate_config
  * vagrant up puppetmaster && vagrant provision puppetmaster 
  * vagrant up *your nodes*



# Vagrant environment

To clean on cluster: rake flush_certs
To restart puppetmaster rake restart_puppetmaster

## puppetmaster
  
Installs a puppetmaster running Ubuntu Precise. It is set up to run on 10.0.0.10 on your host_only network.

Grabs the lastest packages from puppetlabs.

The /etc/puppet/ on the installed puppetmaster is exported to your vagrant environment through /vagrant/puppet.

This means you can edit manifests and modules directly in your <vagrantdir>/puppet/{modules,manifests}.

## puppet clients

Detects OS environments and installs puppet from puppetlabs. Currently supporting ubuntu,centons, sles and rhel.

