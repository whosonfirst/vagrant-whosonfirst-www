# vagrant-whosonfirst-www

This is a vagrant setup for running [whosonfirst-www](https://github.com/whosonfirst/whosonfirst-www) locally in an Ubuntu VM. When you finish, you should be able to run a development version of [whosonfirst.mapzen.com](https://whosonfirst.mapzen.com/) from [localhost:8888](http://localhost:8888/)

We assume you've set these up already (we assume Mac OS X, but it is not a requirement):

* Xcode, from the App Store (mainly for the command line tools like `git`)
* Homebrew https://brew.sh/
* VirtualBox https://www.virtualbox.org/
* Vagrant https://www.vagrantup.com/

Note: this setup assumes that you use a native text editor like [Atom](https://atom.io/) or [TextMate](https://macromates.com/). To make that easier, we will set up a folder sync for the `whosonfirst-www` repo. Making changes to the files in `/usr/local/mapzen/whosonfirst-www` should also update the corresponding files in the VM.

```
sudo mkdir -p /usr/local/mapzen
sudo chown -R $(whoami) /usr/local/mapzen
cd /usr/local/mapzen
git clone https://github.com/whosonfirst/whosonfirst-www.git
git clone https://github.com/whosonfirst/vagrant-whosonfirst-www.git
cd vagrant-whosonfirst-www
make setup
vagrant up
```

Once your machine finishes getting provisioned we can continue setting up `whosonfirst-www`.

```
vagrant ssh
cd /usr/local/mapzen/whosonfirst-www
make setup
```
