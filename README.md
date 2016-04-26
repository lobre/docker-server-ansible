# Docker server ansible

A few ansible script to manage docker proxy and docker apps

https://github.com/loric-/docker-server-proxy

https://github.com/loric-/docker-server-apps

## Configuration

Duplicate, rename and edit `local.sample` or `remote.sample` according to your needs.

## Prepare

Install all the required tools.

    ansible-playbook -i <remote_host> prepare.yml

**Need root access so cannot be used with local host**

## User

Create a user to run docker containers.

    ansible-playbook -i <remote_host> user.yml

**Need root access so cannot be used with local host**

## Update

Update the two repositories (apps and proxy).

    ansible-playbook -i <host> update.yml

After the first update, you should connect to the environment and configure each app by renaming the sample env files.

## Htpasswd

Create a htpasswd for a domain/app.

    ansible-playbook -i <host> -e domain=<mydomain> -e user=<myuser> -e pass=<mypass> htpasswd.yml

## Up

Start the proxy and all the apps.

    ansible-playbook -i <host> up.yml

**CAUTION: the first time, it is advised to launch the proxy manually by following its GitHub documentation.**