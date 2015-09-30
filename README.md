# pl-dev-standup
This is a small set of playbooks that can help bootstrap a dev environment on a non-local instance for the [Powerline Server]() project. Basically, you can use the `dev.yml` playbook to get all of our project dependencies on an instance quickly (say using AWS). The `pl-dev.yml` playbook is used to build a more formal Powerline backend setup. However, this is somewhat coupled with deployment via teamcity so it should not be used for true development purposes. `pl-dev` is also my testing
grounds for messing with how we deploy backend code. So if things break, you've been warned!

## usage
ansible-playbook -i inventory/all dev.yml
