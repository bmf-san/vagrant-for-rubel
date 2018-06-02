# vagrant-for-rubel
This is a vagrant environment for Rubel.

[bmf-san/Rubel](https://github.com/bmf-san/Rubel)

# Get Started
## Provisioning

```console
vagrant init

cd Rubel/ansible/group_vars/vagrant.yml.sample
cp vagrant.yml.sample vagrant.yml

cd Rubel/ansible
cp host.sample host

vagrant provision
```

If you have no vagrant box in your host machine, you need to prepare a vagrant box before `vagrant init`.

An Ansible playbook has been in a directory. Please customize it as necessary.

## Setting a database

```console
vagrant ssh

cd path/to/backend-app

php artisan migration
php artisan db:seed
```

If you want to create data interactively, you can use `php artisan app:init` instead of using `php artisan db:seed`.

After you finished provisioning, you have two databases and three users on the mysql.

User | Password | Database
------------- | ------------- | -------------
root | Pass@Word123 | all
rubel | Pass@Word123 | rubel
rubel_test | Pass@Word123 | rubel_test

You can change the mysql settings by editting the vagrant.yml.

Now you can start the Rubel!

## URL
App | URL
------------- | -------------
Front | http://rubel/
API | http://api.rubel/
Adimin | http://admin.rubel/

## License

This project is licensed under the terms of the MIT license.

## Author

bmf - A Web Developer in Japan.

- [@bmf-san](https://twitter.com/bmf_san)
- [bmf-tech](http://bmf-tech.com/)
