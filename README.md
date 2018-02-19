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
visit and doqnload https://slack.com/downloads/linux  
sudo dpkg -i slack-desktop-3.0.5-amd64.deb  
#############################################################
#### Basic Ubuntu Developer Stack ###
##### curl
sudo apt-get install curl
##### git
sudo apt-get install git  
Please, don't forget to change your_name, your_email, etc stabs to your name / your email. Thank you in advance  
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
##### add your user to www-data group
sudo usermod -a -G www-data <your_username>
#############################################################
#### Usefull Tools ###

To be continued...

