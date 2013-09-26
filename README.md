ansible-playbooks
=================

### Setup Ansible

    sudo aptitude -y install git python-jinja2 python-yaml python-paramiko python-software-properties
    add-apt-repository ppa:rquillo/ansible
    aptitude update && aptitude install ansible
    echo "localhost" > /etc/ansible/hosts

You can now test by typing:

    ansible -c local -m ping all

You should see:

    localhost | success >> {
      "module": "ping",
      "ping": "pong
    }
    
### Run the play

By executing the following, it will setup only the commonly used components:

    ansible-playbook -c local --tags="common" ./create-user.yml
    
You can also just run the run-all script.