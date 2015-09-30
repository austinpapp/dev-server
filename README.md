# pl-dev-standup
This is a small set of playbooks that can help bootstrap a dev environment on a non-local instance for the [Powerline Server]() project. Basically, you can use the `dev.yml` playbook to get all of our project dependencies on an instance quickly (say using AWS). The `pl-dev.yml` playbook is used to build a more formal Powerline backend setup. However, this is somewhat coupled with deployment via teamcity so it should not be used for true development purposes. `pl-dev` is also my testing
grounds for messing with how we deploy backend code. So if things break, you've been warned!

## usage
ansible-playbook -i inventory/all dev.yml

## How To Use
In order to use this, you will need to adjust a few things like IPs and put some keys in certain places. It is also worth noting that we use ubuntu 14.04 trusty for our main instances. Therefore, I need to add a `ansible_become` variable so that i can escalate privileges. That may not be something you need to do. 

### Targets
The `targets` folder is most important in housing your private key for ansible to use under `targets/ssh`. I use `config` and `certs` folders for the `pl-dev.yml` playbook which you don't have to use. It's mainly for our deployment + ansible setup

#### SSH
The `targets/ssh` folder holds the private key needed to connect to the remote instance. However, you can of course change `inventory/all` to point to your private key location. It will default to `target/ssh/` location. 

### IP Updates
In order for ansible to connect to your instance (not mine), you'll need to update your ip or fqdn in `invenotry/all` file.
You use update `ansible_ssh_host=<your_ip>` in that file.

