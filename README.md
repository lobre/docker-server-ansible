# Docker server ansible

A few ansible script to manage docker proxy and docker apps

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

## Htpasswd

Create a htpasswd for a domain/app.

    ansible-playbook -i <host> -e domain=<mydomain> -e user=<myuser> -e pass=<mypass> htpasswd.yml

## Up

    ansible-playbook -i <host> up.yml

Start the proxy and all the apps.