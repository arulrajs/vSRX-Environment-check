# vSRX-Environment-check

Aim is to provide a simple utility for verifying the user Environment against the System Requirements needed for the Juniper's vSRX instances on KVM.

The vSRX system requirements are specified in the [link].
The Utility is based on Ansible framework. User need to install [Ansible] prior using the utility.

###Usage
Download the vSRX_env_check.yaml Script to the server where Ansible is installed.
Create a file 'myhosts' and enter the list of hosts to be checked.

Run command
```sh 
$ ansible-playbook -s vSRX_env_check.yaml --ask-pass -i myhosts
```

This would check below requirements on the provided hosts
* Memory Requirements
* Processor requirements
* Disk Free space
* Virtualization CPU flags
* KVM related packages

The verification result without failure for a host shows all the requirements are matched. 

[link]:http://www.juniper.net/techpubs/en_US/vsrx15.1x49/topics/reference/general/security-vsrx-system-requirement-with-kvm.html
[Ansible]:http://docs.ansible.com/ansible/intro_installation.html
