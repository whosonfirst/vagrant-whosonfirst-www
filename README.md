# vagrant-whosonfirst-www

This is a vagrant setup for running [whosonfirst-www](https://github.com/whosonfirst/whosonfirst-www) in an Ubuntu VM.

This might be the very first thing you do with Who's On First, so we don't assume much of anything about your setup.

But you should have these installed already:

* Xcode, from the App Store (mainly for the command line tools like `git`)
* Homebrew https://brew.sh/
* VirtualBox https://www.virtualbox.org/
* Vagrant https://www.vagrantup.com/

Note: Part of setting up Homebrew involves making `/usr/local` owned by your user account. If you get some permissions errors below, you may need to run `brew doctor` and follow its instructions.

Another note: this assumes that you will be using a "host-based" native text editor like [Atom.app](https://atom.io/) or [TextMate](https://macromates.com/). To make that easier, we set up a folder sync for the `whosonfirst-www` repo. Making changes to the files in `/usr/local/mapzen/whosonfirst-www` should also update the corresponding files in the VM.

```
cd /usr/local
mkdir mapzen
cd mapzen
git clone https://github.com/whosonfirst/whosonfirst-www.git
git clone https://github.com/whosonfirst/vagrant-whosonfirst-www.git
cd vagrant-whosonfirst-www
make build
```

That last command `make build` does three things:

* Copies `Vagrantfile.example` to `Vagrantfile` (which you can modify without worrying about messing up)
* Downloads and runs a new Ubuntu virtual machine
* SSH's you into the new VM
