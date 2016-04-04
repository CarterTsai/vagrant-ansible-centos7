### Vagrant and Ansible Tutorial

Reference:   
1. https://adamcod.es/2014/09/23/vagrant-ansible-quickstart-tutorial.html  
2. http://www.vagrantbox.es/  
3. http://www.slideshare.net/williamyeh/ansible-top-down
4. https://www.nginx.com/resources/admin-guide/load-balancer/
5. http://www.virtualbox.org/manual/ch06.html
6. http://www.virtualbox.org/manual/ch06.html#network_internal
7. http://docs.ansible.com/ansible/file_module.html


### Run Vagrant
This step is create vm for web01 Vagrantfile
* fish shell
```
$> vagrant destroy -f; and vagrant up
```
* bash shell
```
$> vagrant destroy -f && vagrant up
```

```
$> vagrant ssh-config web01
```

### Check All Environment output port
```
$> vagrant port web01
```

### Ping all your nodes
 Reference : [intro_getting_started][1]
```
$> ansible all -m ping
```
or
```
$> ansible all -m ping -u vagrant
```
or
```
$> ansible all -m ping -u vagrant --sudo
```

### Run only playbook to update vm
```
$> ansible-playbook \
    -vvvv \
    --become \
    --user=vagrant \
    -i ./hosts playbook.yml
```

```
$> ansible-playbook -i ./hosts playbook.yml
```

[1]: http://docs.ansible.com/ansible/intro_getting_started.html
