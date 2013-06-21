How to install the latest node.js on Ubuntu?
Posted on October 31, 2012
  15
Node.js is an event-based and non-blocking I/O framework — built on Chrome’s JavaScript engine. Its goal is to provide an easy way to build scalable network programs.

In most linux distributions Node.js is available in a repository which can be accessed via a package manager such as apt-get or aptitude.

However in the repository of the brand new Ubuntu 12.10 (Quantal Quetzal) the nodejs package has the version number 0.6.19 while the current version is 0.8.14 as of this writing. Unfortunately many nodes — that’s how node.js applications are called — are constantly under development and often depend on a newer version.

If you are trying to install a node with the node package manager but providing an old node environment, you most probably expierence a similar error message to the one below.

npm ERR! error installing ws@0.4.22
npm WARN This failure might be due to the use of legacy binary "node" 
npm WARN For further explanations, please read
npm WARN /usr/share/doc/nodejs/README.Debian
npm WARN 

npm ERR! ws@0.4.22 install: `node install.js`
npm ERR! `sh "-c" "node install.js"` failed with 127
npm ERR! 
npm ERR! Failed at the ws@0.4.22 install script.
npm ERR! This is most likely a problem with the ws package,
npm ERR! not with npm itself.
npm ERR! Tell the author that this fails on your system:
npm ERR!     node install.js
npm ERR! You can get their info via:
npm ERR!     npm owner ls ws
npm ERR! There is likely additional logging output above.
npm ERR! 
npm ERR! System Linux 3.5.0-17-generic
npm ERR! command "/usr/bin/nodejs" "/usr/bin/npm" "install" "ws"
npm ERR! cwd /home/slopjong/
npm ERR! node -v v0.6.19
npm ERR! npm -v 1.1.4
npm ERR! code ELIFECYCLE
npm ERR! message ws@0.4.22 install: `node install.js`
npm ERR! message `sh "-c" "node install.js"` failed with 127
npm ERR! errno {}
Update (March 15th, 2013)

At the moment the repository has version 0.8.14 included while the latest version is version 0.10. This tutorial has been updated and successfully tested.

As maintaining old tutorials and old blog posts costs time, feel free to donate me a virtual beer. Drop me a message here and tell me what your favourite donation channel is (like flattr whehere I haven’t an account yet).

Preparation

The nodejs package depends on a couple of other packages, be sure that you have the repository component universe enabled.

# in /etc/apt/sources.list
deb http://archive.ubuntu.com/ubuntu quantal main restricted universe
deb http://security.ubuntu.com/ubuntu quantal-security main restricted universe
deb http://archive.ubuntu.com/ubuntu quantal-updates main restricted universe
After enabling it run sudo apt-get update.

Installation steps

In order to get a more recent nodejs version you need to add a personal package archive (ppa) and update the package index files. To do so open Terminal and execute the following commands.

sudo apt-get install python-software-properties
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get install nodejs
Pay attention to the second line, if you are trying to execute apt-apt-repository you won’t have luck.

Install the node package manager

Update (March 15th, 2013)
You no longer need to install npm separately as nodejs includes it now.

To manage your nodes it’s recommended to install the node package manager (npm) too.

sudo apt-get install npm
Who prefers to compile npm from its sources will find this script very useful.

Update (March 20th, 2013)
It looks like somebody forgot to pay his bill. The link to the script is currently broken.

Update (April 15th, 2013, 19:50 UTC+2)
A guy from Israel has grabbed the domain which has expired three and a half hours ago.

Read related articles: javascript Node.js Ubuntu
24 COMMENTS

Rufus
Posted November 19, 2012 at 9:06 PM
Thanks!!! this worked for me.

Just pasting my old error so others will find this solution too.

# ws@0.4.22 install /home/......./ttys/node_modules/tty.js/node_modules/socket.io/node_modules/socket.io-client/node_modules/ws
# node install.js

sh: 1: node: not found
npm ERR! error installing ws@0.4.22
npm WARN This failure might be due to the use of legacy binary "node"
npm WARN For further explanations, please read
npm WARN /usr/share/doc/nodejs/README.Debian
npm WARN
npm ERR! error installing socket.io-client@0.9.10
npm ERR! error installing socket.io@0.9.10
npm ERR! error installing tty.js@0.2.8

npm ERR! ws@0.4.22 install: `node install.js`
npm ERR! `sh "-c" "node install.js"` failed with 127
npm ERR!
npm ERR! Failed at the ws@0.4.22 install script.
npm ERR! This is most likely a problem with the ws package,
npm ERR! not with npm itself.
npm ERR! Tell the author that this fails on your system:
npm ERR!     node install.js
npm ERR! You can get their info via:
npm ERR!     npm owner ls ws
npm ERR! There is likely additional logging output above.
npm ERR!
npm ERR! System Linux 3.5.0-18-generic
npm ERR! command "/usr/bin/nodejs" "/usr/bin/npm" "install" "tty.js"
npm ERR! cwd /home/wouterdb/install/ttys
npm ERR! node -v v0.6.19
npm ERR! npm -v 1.1.4
npm ERR! code ELIFECYCLE
npm ERR! message ws@0.4.22 install: `node install.js`
npm ERR! message `sh "-c" "node install.js"` failed with 127
npm ERR! errno {}
npm ERR!
npm ERR! Additional logging details can be found in:
npm ERR!     /home/wouterdb/install/ttys/npm-debug.log
npm not ok