# Setting Up Your WordPress Development Environment

---

## Mac

On a Mac, we recommend setting up VVV.  However, we have provided the instructions for setting up MAMP in the event that you are unable to successfully setup VVV on your machine.

### Varying Vagrant Vagrants (VVV)
- Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- Download and install [Vagrant](https://www.vagrantup.com/)
- Open up the terminal and run these commands to install the recommended vagrant plugins
	- `vagrant plugin install vagrant-hostsupdater`
	- `vagrant plugin install vagrant-triggers`
- Clone or extract the VVV project into a local directory:
	- Run `git clone git://github.com/Varying-Vagrant-Vagrants/VVV.git vagrant-local`
	- OR download and extract a stable release [zip file](https://github.com/varying-vagrant-vagrants/vvv/releases) to a `vagrant-local` directory on your computer.
- In the terminal, navigate to the `vagrant-local` directory and run `vagrant up`.  This will start the provisioning process, which takes a while the first time you run it... so be patient and let it finish.
- Once the provisioning is finished, you can visit `http://local.wordpress.dev` in your browser.  You will be able to login to WordPress using `admin` as the username and `password` as the password.
- If you run into any trouble, consult the [VVV documentation](https://github.com/Varying-Vagrant-Vagrants/VVV/blob/master/README.md).

### MAMP
- Download and install [MAMP](http://www.mamp.info/en/downloads/)
- Create a `localhost` folder in your user directory or in an easily accessible location of your choice.
- Start MAMP and then:
	- Click the 'Preferences...' button
	- Go to the 'Apache' tab
	- Update the document root to point to your `localhost` directory
	- Start (or restart) the server once you return to the main screen
- Setup a new database by:
	- Clicking 'Open start page' from the main MAMP screen
	- Click the 'phpMyAdmin' link at the top of the page
	- In the 'Create new database' field, type in `wordpress` and click the 'Create' button
- Download [WordPress](https://wordpress.org/download/) into your `localhost` directory and extract the .zip file
- Navigate to [http://localhost:8888/](http://localhost:8888/) and click on the 'wordpress' link
- Click the 'Create a configuration file' button and enter the following information when requested:
	- Database name -- wordpress
	- User name -- root
	- Password -- root
- Continue through the WordPress setup screens until you are done.
- To enable pretty permalinks, you will need to open up the Apache `/Applications/MAMP/conf/apache/httpd.conf` file and remove the `#` symbol before this line: `LoadModule rewrite_module modules/mod_rewrite.so`.  Then, restart the server via the main MAMP screen.
- If you feel the need to have a custom domain (e.g. local.wordpress.dev), just follow [this tutorial](http://blainsmith.com/articles/quick-and-dirty-local-domain-names-for-mamp/).  However, be sure to skip step 2 since you've already done it and use the full path to your `localhost` directory as the `VirtualDocumentRoot` in step 3.  If you add additional sites, you will only need to do step 1 as the other steps only need to be done once.
- If you are more of a visual learner, follow these [installation instructions](http://www.smashingmagazine.com/2011/09/28/developing-wordpress-locally-with-mamp/) or watch this [video tutorial](https://www.youtube.com/watch?v=sNRBnX6CtXE).

## Windows

### Varying Vagrant Vagrants (VVV)
- Due to the complexities associated with setting up VVV on Windows, we recommend just installing WAMP as defined below.

### WAMP
- Follow these [installation instructions](http://premium.wpmudev.org/blog/how-to-set-up-wordpress-locally-for-pcwindows-with-wamp/).  Just ignore the section titled 'Setting up WordPress Multisite'.