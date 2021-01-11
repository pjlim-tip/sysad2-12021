## How to create an Ansible Configuration
1. Make sure ansible is downloaded already. To check if it is, type:  
   `ansible --version`
2. To create a configuration file simply type:  
   `touch ansible.cfg`
3. To edit `ansible.cfg`, execute the `vim ansible.cfg` command. Then press `i` key  
   **Note: Vim is a text editor. So, executing `vim ansible.cfg` can also create the file  
   even if it is not yet created**  
4. The usual/default contents of ansible.cfg is as follows:  
   ```shell
   [defaults]  
     
   inventory = .<pathname of your inventory>
   remote_user = <your ssh user>
   ```
5. To save the changes you have made, press the `Esc` key and then, enter `:wq!` 

## How to create an Ansible Inventory
1. The procedure is the same with creating the `ansible.cfg` file but replacing the "ansible.cfg"  
   with the desired file name of inventory
   `vim inventory`
2. This file should contain the IP addresses and hostnames of your remote hosts or the hosts you  
   would like to connect to via ssh.
   ```
   [<group name>]
   ansible_host=<IP address> ansible_ssh_user=<username>
   ```
3. Save the changes you have made by pressing `Esc` key and by typing `:wq!` afterwards.

## How to create an Ad-hoc Ansible command with _setup_ and _shell_ module  
   After creating configuration and inventory files, ad-hoc ansible commands are now ready to use  
1. An example of ad-hoc command will be:  
   ``ansible all -m ping``
   where:  
   `all` is the target host or group hosts   
   `-m` is the module used; and  
   `ping` is the parameter used
2. To use setup module:  
   ``ansible <group name/target host> -m setup -a "gather_subset=!any"``
3. To use shell module, an example would be knowing the hostname of the target host:  
   ``ansible <group name/target host> -m shell -a "hostname"``
