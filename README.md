# Open edX server-vars.yml
## Overview
This repo will contain sane default values (mostly from the [Configuration repo](https://github.com/edx/configuration)) that can be easily overridden for production installations.

## To use
1. Use `curl`, `wget` or some other utility to copy the server-vars.yml file from this repo onto the server that will run the `ansible-playbook` command. 
2. Rewrite the `ansible-playbook` command to include this file for the provisioning process.

e.g.:
```
ssh MY_NEW_SERVER

# after connecting to server
# install ansible, dependencies, etc. in a virtualenv
...
...

# grab the file from this repo
curl https://raw.githubusercontent.com/tkeemon/openedx-server-vars/master/server-vars.yml -o /tmp/server-vars.yml

# begin ansible-playbook provisioning
cd /tmp/configuration/playbooks 
sudo ansible-playbook -i localhost, -c local edx_sandbox.yml -e@/tmp/server-vars.yml
```

## TODO: 
- tag commits in this repo to keep in line with named-releases
- update installation docs in Github/Confluence to include this repo

