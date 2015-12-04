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
  git clone --recursive https://github.com/mark-dce/sufia-prod-ubuntu-vagrant.git
  ```
3. Change directory into your new project directory  
  ```
  cd sufia-prod-ubuntu-vagrant
  ```
4. Start the VM using  
  ```
  vagrant up
  ```
5. Wait for the provisioning script to complete - this can take some time
   (30 minutes to a few hours) depending on your internet connection and processor speed
6. Congratulations, you should now have a running Sufia repository running at  
   [http://localhost:8484](http://localhost:8484)
