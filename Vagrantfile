# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 8082, host: 8082
  
  config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     sudo apt-get install -y git
     sudo apt-get install -y nodejs

     sudo gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
     curl -L https://get.rvm.io | bash -s stable --ruby
     source /usr/local/rvm/scripts/rvm
     rvm get stable --autolibs=enable
	 rvm install ruby
     rvm --default use ruby-2.2.1
     gem install jekyll
     
     jekyll new /vagrant/testsite
     
     # simple start jekyll on testsite
     cd /vagrant/testsite; jekyll serve -P 8082 -H 0.0.0.0 --detach
     
  SHELL
  
  
  #config.vm.provision :shell,
  #  :inline => "sudo apt-get update && sudo apt-get -y install build-essential git ruby1.9.3 && sudo gem install github-pages therubyracer --no-ri --no-rdoc"

  #config.ssh.forward_agent = true
end
