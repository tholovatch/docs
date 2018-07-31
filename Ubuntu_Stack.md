#### This is basic stack of apllication, services, etc one may find usefull working on Ubuntu 16.04 LTS. It is not like any of those is required except Slack (communication) and git (control version system). So if you are very old school [cat](https://www.urbandictionary.com/define.php?term=Cat&defid=668457) or very old school [Kate](https://www.urbandictionary.com/define.php?term=Kate) and prefer using Sublime or even Notepad as code editor - welcome. But. You are on your own then. No how - can - I - toggle - between - scripts - in - my - precious - sublime questions. One can't pretend being old school. Ok, sorry, one can, but that is <s>intolerant remark was here</s> - even if no money involved. Be safe, rtfm, and don't eat the yellow snow.
#### V.I.P.S. And please, please, please, don't forget to take shower, clean teeth, change T-shirts/panties, etc in time. We are trying to build dream team here. So only person allowed to be either incompetent or sloppy is this script's author. Nevermind him.
#############################################################
#### Basic Ubuntu Stack ####
##### Skype
dpkg -s apt-transport-https > /dev/null || bash -c "sudo apt-get update; sudo apt-get install apt-transport-https -y"  
echo "deb [arch=amd64] https://repo.skype.com/deb stable main" | sudo tee /etc/apt/sources.list.d/skypeforlinux.list  
sudo apt-get update  
sudo apt-get install skypeforlinux
##### Chrome
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb  
sudo dpkg -i --force-depends google-chrome-stable_current_amd64.deb
##### Synaptic package manager
sudo apt-get install synaptic
##### Slack
*visit and download https://slack.com/downloads/linux*  
sudo dpkg -i slack-desktop-3.0.5-amd64.deb  
#############################################################
#### Basic Ubuntu Developer Stack ###
##### curl
sudo apt-get install curl
sudo apt-get install libcurl4-gnutls-dev
# or
sudo apt-get install libcurl4-openssl-dev
# depending on whether you want to use gnutls or openssl for SSL.
##### git
sudo apt-get install git  
*Please, don't forget to change your_name, your_email, etc stabs to your name / your email. Thank you in advance*  
git config --global user.name "your_name"  
git config --global user.email "your_email"  
ssh-keygen -t rsa -b 4096 -C "your_email"  
eval "$(ssh-agent -s)"  
ssh-add ~/.ssh/id_rsa
##### mysql
sudo apt-get install mysql-server  
mysql_secure_installation
##### postgresql
sudo apt-get install postgresql postgresql-contrib  
sudo su - postgres -c "createuser -s $USER"  
#############################################################
#### Basic Ubuntu Developer Web Stack ###
##### apache
sudo apt-get install apache2  
sudo a2enmod rewrite
##### nginx
sudo apt-get install nginx
##### add your user to www-data group
sudo usermod -a -G www-data <your_username>
##### nodejs and npm
sudo wget -qO- https://deb.nodesource.com/setup | bash -  
sudo apt-get install -y nodejs  
sudo apt-get install npm -y  
sudo ln -s /usr/bin/nodejs /usr/bin/node  
### Use n module from npm in order to upgrade node
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
#############################################################
#### Python Developer Stack ###
##### essentials
sudo apt-get install python-pip  
sudo pip install virtualenv  
sudo apt install build-essential python3-dev libxslt-dev libzip-dev libldap2-dev libsasl2-dev python-dev  
sudo apt-get install pylint  

##### IDE
sudo snap install pycharm-professional --classic  
*That is great commercial IDE from jetbrains*  
sudo snap install pycharm-community --classic    
*That is great freeware version from jetbrains*  
#############################################################
#### Php Developer Stack ###
##### essentials - php5.6 and php7.2
sudo add-apt-repository ppa:ondrej/php  
sudo apt-get update  
sudo apt install php5.6  
sudo apt install php7.2  
sudo apt install php5.6-cli php5.6-xml php5.6-mysql php5.6-mcrypt php5.6-gd  
sudo apt install php7.2-cli php7.2-xml php7.2-mysql php7.2-mcrypt php7.2-gd  
*You can install other modules analogically. And switch between versions using following commands. Note there will be 2 different php.ini files in corresponding folders.*  
sudo update-alternatives --set php /usr/bin/php5.6    
sudo a2dismod php7.2  
sudo a2enmod php5.6  
##### IDE
sudo snap install phpstorm --classic  
*That is great commercial IDE from jetbrains*  
#############################################################
#### Usefull Tools ###
##### docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"  
sudo apt-get update  
apt-cache policy docker-ce  
sudo apt-get install -y docker-ce  
sudo systemctl status docker  
sudo curl -L https://github.com/docker/compose/releases/download/1.19  .0/docker-compose-\`uname -s\`-\`uname -m\` -o /usr/local/bin/docker-compose  
sudo chmod +x /usr/local/bin/docker-compose  
##### Visual database management tool for Mysql 
sudo apt-get install mysql-workbench  
*Note that mysql workbench is UNIX-native and quite sufficient while you are doing simple things. But if you need to perform complex migrations on big data amounts - you need smth else. Best tool I've seen is SQLyog. However it have no UNIX version and is absolutely commercial. Still there exists Wine-based solution, and other solutions that shouldn't be mentioned in decent society. Not that i am sure we are kind of. But anyway ubuntu-wine-sqlyog is out of this tutorial scope.*
##### General visual database management tool 
sudo snap install datagrip --classic   
*Note that is commercial solution. Good one tho.*
##### Screenshot management app - shutter
sudo add-apt-repository ppa:ubuntuhandbook1/apps  
sudo apt-get update  
sudo apt-get install shutter  
*feel free to notify in case you know better one*  
##### Image editor - gimp
sudo add-apt-repository ppa:otto-kesselgulasch/gimp-edge  
sudo apt-get update  
sudo apt install gimp gimp-gmic  
*feel free to notify in case you know better one*  


To be continued...

