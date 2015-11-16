# Sufia Demo VM
This repsoitory builds a Vagrant based VM which runs a demo instance of Sufia.  The VM provides a fully configured
Sufia server that can be used for evaluation and demo purposes.  Please do not use this VM for actual production use; 
most of the security credentials and passwords in use are checked into source control and easily identifiable.  If you need
help installing a true production instance of Sufia, please either reach out to the Hydra Tech list (hydra-tech@googlegroups.com) 
or contact DCE ([http://curationexperts.com](http://curationexperts.com)).

### Using this repository
1. Install VirtualBox and Vagrant on your target machine.
2. Clone the code to your local machine:
```
git clone https://github.com/mark-dce/sufia-prod-ubuntu-vagrant.git
cd sufa-prod-ubuntu-vagrant
```
3. Start the VM using `vagrant up`
4. Connect to the demo at http://localhost:8484