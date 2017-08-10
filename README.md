# WP Staging Ansible

WordPress staging environment on UpCloud with Ansible.

## Adding a site:
1. Copy `secrets.yml.example` to `secrets.yml` and add information (found from 1pwd) to it
2. Add site information to `sites.yml`
3. Run `ansible-playbook -i hosts -u root main.yml` **NOTE!** Your public keyfile should've been added to server before running this command.

## Capistrano deployment
Variables for WordPress env-file (which is used by Capistrano on non-Pantheon cases):

```
STAGING_SERVER=94.237.40.223
STAGING_USER=www
STAGING_FOLDER=/srv/sites/[SITENAME] // [SITENAME] defined in sites.yml
```
