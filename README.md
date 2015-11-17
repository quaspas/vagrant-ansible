Setup
-----

Make a virtual environment using virtualenv and virtualenvwrapper:

    mkvirtualenv ansible

Install ansible:

    pip install ansible 

Start vagrant box:

    vagrant up

Add the a `repo` in `vars/app.yml`.

Add you ssh keys to the vm:

    ansible-playbook ssh-add-key.yml --ask-pass
        
(defualt password is `vagrant`)
        
Install all kinds of stuff for the box:

    ansible-playbook vagrant-playbook 

Gotchas
-------


    fatal: [192.168.33.10] => {'msg': "FAILED: ('192.168.33.10', <paramiko.rsakey.RSAKey object at 0x1053b7d90>, <paramiko.rsakey.RSAKey object at 0x1053b1f90>)", 'failed': True}
    FATAL: all hosts have already failed -- aborting

Remove 192.168.33.10 line from known_hosts:

    vi ~/.ssh/known_hosts
