# Badzilla Lightweight Docker App Development VM

This is a lightweight VM in which you can develop your Docker apps in a consistent Ubuntu 20.04LTS environment.

It is ideal for small dev teams and solo developers who prefer to develop in a VM to avoid having to pollute their host 
disk drives with multiple configurations and products. 

The VM has little functionality (although happy to accept Pull Requests) but contains the docker-ce engine, Python3, Node, and 
AWS tooling so it is ideal for those apps that will ultimately be hosted on AWS.

The VM uses Vagrant and Ansible for orchestration, and VirtualBox. Note therefore until Oracle 
change their stance, it won't work on Mac M1 machines. 

I have only tested this on my ancient 2015 MBP.

## FAQ

***Can't I just use my Macbook Pro natively? Why do I need this?***

Yes you can of course. This just provides a consistent, command line Linux experience for those who
prefer that approach. 

***Does it actually work?***

It does for me! But don't take my word for it. I wrote a blog on getting a simple PHP Apache Docker build working that 
output `phpinfo()` data. It will take you 5 minutes to follow my process. Once you've installed the VM, `ssh` into it and follow what I did 
in [Docker phpinfo()](https://badzilla.co.uk/index.php/programmatically-create-aws-ecr-repository-and-commit-docker-image-ecr) 

When you get to the final relevant step, change
```bash
docker run -d -p 8080:80 d8codebase
```
for:
```bash
docker run -d -p 9090:80 d8codebase
```
since this VM is port-forwarding on 9090. Do that then point a browser to http://127.0.0.1:9090 and you'll see the `phpinfo()` screen. It works!!

### Dependencies

Install [Vagrant](https://www.vagrantup.com/downloads), [virtualBox](https://www.virtualbox.org/wiki/Downloads), and [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

Copy the file local-config.yml.saved to local-config.yml
```bash
cp local-config.yml.saved local-config.yml
```
### Local Configuration *Must Read*
If you are using AWS then populate out the AWS keys and region variables in the `local-config.yml` file.

If you are working in an office with other colleagues you must ensure that IP addresses on VMs don't clash. 
Go to the `Vagrantfile` file and change the `192.168.78.107` value to something unique on the last number.

Whilst in the `Vagrantfile` change the shared drive directories in the `config.vm.synced_folder` value. This will typically
be the top level directory where you have all your dev repos. Don't change the `/opt/` part! This is where
you'll find the repos in the VM.

Start the VM
```bash
vagrant up
```

SSH into the VM
```bash
vagrant ssh
```

When you have finished for the day, ctrl-D to log out of the VM and issue
```bash
vagrant halt
```

Enjoy! 