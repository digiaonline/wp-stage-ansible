# WP Staging Ansible

WordPress staging environment on UpCloud with Ansible.

## Adding a site:
1. Copy `secrets.yml.example` to `secrets.yml` and add information (found from 1pwd) to it
2. Add site information to `sites.yml`
3. Run `ansible-playbook -i hosts -u root create.yml` **NOTE!** Your public keyfile should've been added to server before running this command.

## Deleting a site:
1. Delete site information from `sites.yml`
2. Run `ansible-playbook -i hosts -u root delete.yml -e delete_site=[SITE_TO_DELETE]` where `[SITE_TO_DELETE]` is the site name **NOTE!** This command wipes out everything (DB, nginx-conf, public-folder) from remote!

## Capistrano deployment
Variables for WordPress env-file (which is used by Capistrano on non-Pantheon cases):

```
STAGING_SERVER=94.237.40.223
STAGING_USER=www
STAGING_FOLDER=/srv/sites/[SITENAME] // [SITENAME] defined in sites.yml
```
