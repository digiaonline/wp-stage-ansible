# WP Staging Ansible

WordPress staging environment on UpCloud with Ansible.

### Adding a site:
1. Copy `secrets.yml.example` to `secrets.yml` and add information (found from 1pwd) to it
2. Add site information to `sites.yml`
3. Run `ansible-playbook -i hosts -u root main.yml` **NOTE!** You should have added your public keyfile to server before running this command.
