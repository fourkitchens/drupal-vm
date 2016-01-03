## Ansible Scripts

Ansible deployment scripts, located in the ```deploy``` directory can be used for common deployment tasks. Deployment commands can be run on a development server using the following syntax, however to use them in a Vagrant virtual machine you'll need to use the bash script located below.

    ansible-playbook -i hosts deploy/user-add.yml

Fill out the prompts or include them in the extra-vars ```-e``` argument

    ansible-playbook -i hosts -e="user_name=bender github=fkbender" deploy/user-add.yml

A special bash script is available that makes it possible to run deployment scripts locally.

    ./vagrant-playook deploy/user-add.yml

The following commands will work on the vagrant machine and on the dev server:

### Databases
Create MySQL Database

    ./vagrant-playbook deploy/database/mysql-db-create.yml

Import MySQL Database

    ./vagrant-playbook deploy/database/mysql-db-import.yml

### Solr Cores

Add Solr Core  

    ./vagrant-playbook deploy/solr-cores/solr-core-add.yml

Delete Solr Core  

    ./vagrant-playbook deploy/solr-cores/solr-core-delete.yml

### Users

Add User

    ./vagrant-playbook deploy/users/user-add.yml

Delete User

    ./vagrant-playbook deploy/users/user-delete.yml

### Drupal Sites

The following commands only work on a remote dev server:

Deploy Drupal dev site

    deploy/drupal-sites/drupal-dev-site-deploy.yml

Remove Drupal dev site

    deploy/drupal-sites/drupal-dev-site-remove.yml

Deploy Drupal trunk site

    deploy/drupal-sites/drupal-trunk-site-deploy.yml

Remove Drupal trunk site

    deploy/drupal-sites/drupal-trunk-site-remove.yml
