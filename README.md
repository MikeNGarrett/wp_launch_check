![WPLC Logo](https://pantheon.io/sites/default/files/wplc.png)

# WP Launch Check
WP Launch Check is an extension for WP-CLI designed for Pantheon.io customers. While designed initially for the Pantheon dashboard it is intended to be fully usable outside of Pantheon. 

To use WP Launch Check simply run the ```wp launchcheck <subcommand>``` command like you would any other WP-CLI command.

For more information about WP-CLI you can visit [their github page](https://github.com/wp-cli/wp-cli). 

WP Launch Check should be considered in "BETA". Many of the checks have still not been tested in the wild. If you experience a problem please open an issue. 

## Local install

Grab this repo and place in the web root for your local site. Run these commands from within ```wp_launch_check-master```
We reocommend using composer to handle dependencies setup. See [Composer installation instructions](https://getcomposer.org/download/) for more information. 

Run ```composer install```
Run ```bash bin/prepare.sh```
Start using ```wp``` with the new launchcheck. Example: ```wp --require=wp_launch_check.phar launchcheck all```


## Available commands

Below is a summary of the available commands. *Full technical description of each check run by each command can be found in the [CHECKS.md](CHECKS.md)*

  * **wp launchcheck cron** : Checks whether cron is enabled and what jobs are scheduled
  * **wp launchcheck general**: General checks for data and best practice, i.e. are you running the debug-bar plugin or have WP_DEBUG defined? This will tell you. 
  * **wp launchcheck database**: Checks related to the databases.
  * **wp launchcheck objectcache**: Checks whether obect caching is enabled and if on Pantheon whether redis is enabled.
  * **wp launchcheck sessions**: Checks for plugins refering to the php session_start() function or the superglobal ```$SESSION``` variable. In either case, if you are on a cloud/distributed platform you will need additional configuration achieve the expected functionality
  * **wp launchcheck secure**: Does some rudimentary security checks
  * **wp launchcheck plugins**: Checks plugins for updates and known vulnerabilities




