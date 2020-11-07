# Take complete control of your RPi k3s cluster.
- Prepares your RPi nodes by updating deps, upgrading apt, setting cgroups and swap settings.
- Easily install the latest version of k3s. Or specify a version in Group/Vars.
- Option to completly wipe the previous k3s install.
- Currently configured for Debian OS and systemd.  Alpine and openrc next.
- Kubeconfig file is copied to local working dir.  Check the files folder in this repository for your working k3s.yml file.
- Cluster is restarted and ready for management after this playbook is deployed.  Enjoy, its that easy. 
- Simply run ```cd ansible && make```

# Minimal Initial HW Provisioning
- Set-up your RPi's with the latest Raspbian Image. Stretch and Buster work fine. 
- Give your RPi's some passowords and hostnames, use the "sudo raspi-config" command.
- Copy ssh keys over to all devices. ```ssh-copy-id username@pi_hostname.address```
- Create Host entries in your local computers ```.ssh/config``` file.

# K3S
- List your master and nodes in the ```hosts.ini``` file.
  - Use the HostName that was entered in .ssh/config.
  - For the master, you must also specifiy the local IP address in ```ansible_host=192.168.0.1/24```
- Changing the k3s version and Full clean Install is found in ```group_vars/all.yaml```
  - ```full_clean_install: True``` will wipe the currently installed k3s server and node configurations.
- Set agents and server options in service files. ```roles/k3s/master/template``` and ```roles/k3s/node/template```

# make
- Use the command ```make``` to run the ansible playbook
- When completed, the kubeconfig ```k3s.yml``` file can be found in the ```files``` directory of this project. 
