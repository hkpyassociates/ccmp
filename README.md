# RabbitMQ 

###  Step 2 – Install Erlang

First, use the following commands to add Erlang yum repository on RHEL based system. You can simply download Erlang repository package from its official website and install on your system.

```bash
wget https://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm
sudo rpm -Uvh erlang-solutions-1.0-1.noarch.rpm
```
Now, you can install Erlang package on your system using the following command. This will install all of its dependencies as well.

```bash
sudo yum install erlang erlang-nox
```
### Step 2 – Install RabbitMQ Server

After installing requirements, now download the RabbitMQ rpm package as per your operating system version from its official website.
CentOS/RHEL 7 & Fedora >= 19

```bash
$ wget https://www.rabbitmq.com/releases/rabbitmq-server/v3.6.9/rabbitmq-server-3.6.9-1.el7.noarch.rpm
```
After downloading the RabbitMQ server package, import rabbitmq signing key and install it using the following commands.

```bash
$ sudo rpm --import https://www.rabbitmq.com/rabbitmq-release-signing-key.asc
$ sudo yum install rabbitmq-server-3.6.9-1.el7.noarch.rpm
```
### Step 2 – Manage RabbitMQ Service

After completing above installations, enable the RabbitMQ service on your system. Also, start the RabbitMQ service. Use one the below methods sysvinit for older systems or systemctl for the latest operating system.
Uisng Systemctl – CentOS/RHEL 7 & Fedora >= 19

```bash
$ sudo systemctl enable rabbitmq-server
$ sudo systemctl start rabbitmq-server
```

# Install MongoDB

### Step 1 – Adding the MongoDB Repository
The mongodb-org package does not exist within the default repositories for CentOS. However, MongoDB maintains a dedicated repository. Let's add it to our server.

With the vi editor, create a .repo file for yum, the package management utility for CentOS:

```bash
$ sudo vi /etc/yum.repos.d/mongodb-org.repo
```

Then, visit the Install on Red Hat section of MongoDB’s documentation and add the repository information for the latest stable release to the file:

```bash
[mongodb-org-3.4]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-3.4.asc
```
Save and close the file.

Before we move on, we should verify that the MongoDB repository exists within the yum utility. The repolist command displays a list of enabled repositories:

```bash
yum repolist
```

Output:

```bash
. . .
repo id                          repo name
base/7/x86_64                    CentOS-7 - Base
extras/7/x86_64                  CentOS-7 - Extras
mongodb-org-3.2/7/x86_64         MongoDB Repository
updates/7/x86_64                 CentOS-7 - Updates
. . .
```
With the MongoDB Repository in place, let's proceed with the installation.

### Step 2 – Install MongoDB

We can install the mongodb-org package from the third-party repository using the yum utility.

```bash
sudo yum install mongodb-org
```

There are two Is this ok [y/N]: prompts. The first one permits the installation of the MongoDB packages and the second one imports a GPG key. The publisher of MongoDB signs their software and yum uses a key to confirm the integrity of the downloaded packages. At each prompt, type Y and then press the ENTER key.

Next, start the MongoDB service with the systemctl utility:

```bash
sudo systemctl start mongod.service
```

The stop command halts all running mongod processes.

```bash
sudo systemctl stop mongod.service
```

# Install Nodejs

First of all, You need to enable node.js yum repository in your system provided by the Node.js official website. You also need development tools to build native add-ons to be installed on your system.

```bash
yum install -y gcc-c++ make
curl -sL https://rpm.nodesource.com/setup_8.x | sudo -E bash -
```
After adding yum repository in your system lets install Node.js package. NPM will also be installed with node.js. This command will also install many other dependent packages on your system.

```bash
sudo yum install -y nodejs
```

To check that the installation was successful, you can ask Node to display its version number:

```bash
node --version
```

```bash
v10.16.0
```

```bash
npm --version
```

```bash
6.9.0
```

# Install Git

Use yum, CentOS's native package manager, to search for and install the latest git package available in CentOS's repositories:

```bash
sudo yum install git
```

```bash
git --version
```
```bash
git version 1.8.3.1
```

# Install pm2

```bash
sudo npm install -g pm2
```

# Install Gulp-cli

```bash
sudo npm install -g npm i gulp-cli
```

# Install Angular-cli

```bash
sudo npm install --unsafe-perm -g @angular/cli@6.2.3
```
To check that the installation was successful, you can ask Angular-cli to display its version number:

```bash
ng --version
```

```bash
     _                      _                 ____ _     ___
    / \   _ __   __ _ _   _| | __ _ _ __     / ___| |   |_ _|
   / △ \ | '_ \ / _` | | | | |/ _` | '__|   | |   | |    | |
  / ___ \| | | | (_| | |_| | | (_| | |      | |___| |___ | |
 /_/   \_\_| |_|\__, |\__,_|_|\__,_|_|       \____|_____|___|
                |___/
    

Angular CLI: 6.2.3
Node: 10.16.0
OS: linux x64
Angular: 
... 

Package                      Version
------------------------------------------------------
@angular-devkit/architect    0.800.3
@angular-devkit/core         8.0.3
@angular-devkit/schematics   8.0.3
@schematics/angular          8.0.3
@schematics/update           0.800.3
rxjs                         6.4.0
```

# Install Python

Before we begin with the installation, let's make sure to update the default system applications to have the latest versions available.

We will be using the open-source package manager tool yum, which stands for Yellowdog Updater Modified. This is a commonly used tool for working with software packages on Red Hat based Linux systems like CentOS. It will let you easily install and update, as well as remove software packages on your computer.Let’s first make sure that yum is up to date by running this command:

```bash
sudo yum -y update
```


Next, we will install yum-utils, a collection of utilities and plugins that extend and supplement yum:

```bash
sudo yum -y install yum-utils
```

Finally, we’ll install the CentOS Development Tools, which are used to allow you to build and compile software from source code:

```bash
sudo yum -y groupinstall development
```

### Installation

We will install the most current upstream stable release of Python 3, we will need to install IUS, which stands for Inline with Upstream Stable. A community project, IUS provides Red Hat Package Manager (RPM) packages for some newer versions of select software.

To install IUS, let’s install it through yum:

```bash
sudo yum -y install https://centos7.iuscommunity.org/ius-release.rpm
```

Once IUS is finished installing, we can install the most recent version of Python:

```bash
sudo yum -y install python36u
```

When the installation process of Python is complete, we can check to make sure that the installation was successful by checking for its version number with the python3.6 command:

```bash
python3.6 -V
```
With a version of Python 3.6 successfully installed, we will receive the following output:

```bash
Python 3.6.1
```

We will next install pip, which will manage software packages for Python:
```bash
sudo yum -y install python36u-pip
```

Finally, we will need to install the IUS package python36u-devel, which provides us with libraries and header files we will need for Python 3 development:
```bash
sudo yum -y install python36u-devel
```
Collapse
