# Take complete control of your RPi k3s cluster.
- Prepar your RPi nodes by updating deps, upgrading apt, setting cgroups and swap settings.
- Easily install the latest version of k3s. Or specify a version in Group/Vars.
- Completly wipe the previous k3s install by setting fresh_clean_install to true.
- Currently configured for Debian OS and systemd.  Alpine and openrc next.
- Kubeconfig file is copied to local working dir.  Check the files folder in this repository for your working k3s.yml file.
- Cluster is restarted and ready for management after this playbook is deployed.  Enjoy, its that easy. "Make".

# Minimal Initial HW Provisioning
- Set-up your RPi's with the latest Raspbian Image. Stretch and Buster work fine. 
- Give your RPi's some passowords and hostnames, use the "sudo raspi-config" command dummy.
- You gotta copy some ssh keys over. ```ssh-copy-id username@pi_hostname.address``` 

# K3S
- szet agents and server options in service files.
