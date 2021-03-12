## Setup MongoDB on Mac

### Install MongoDB server (db tools included)

Install xcode tools

```
brew tap mongodb/brew
brew install mongodb-community
```

If following error shows during install 
```
Error: The `brew link` step did not complete successfully
The formula built, but is not symlinked into /usr/local
Could not symlink bin/install_compass
Target /usr/local/bin/install_compass
```

Then you can run following command to rectreate symbolic links
```
brew link --overwrite mongodb-community
```

This will install **mongod server**, **mongos sharded cluster query router** and **mongo shell**

Also it will create the following files and directories at the location specified below, depending on your Apple hardware:

|   | Intel Processor | Apple M1 Processor |
|-|-|-|
| configuration file | /usr/local/etc/mongod.conf | /opt/homebrew/etc/mongod.conf |
| log directory | /usr/local/var/log/mongodb | /opt/homebrew/var/log/mongodb |
| data directory | /usr/local/var/mongodb | /opt/homebrew/var/mongodb |


### Manage MongoDB server as service

Run service now without registering it to launch at login (or boot)
```
brew services run mongodb-community
```

Start service now and register it to launch at login (prepend 'sudo' to launch at boot)
```
brew services start mongodb-community
```

Restart service now and register it to launch at login (prepend 'sudo' to launch at boot)
```
brew services restart mongodb-community
```

Stop service now and unregister it from launch at login (prepend 'sudo' to launch at boot)
```
brew services stop mongodb-community
```

Check mongodb service status

```
brew services list
```

Create some aliases (not mandatory)
```
echo "alias mongod='brew services run mongodb-community'
alias mongod-status='brew services list'
alias mongod-stop='brew services stop mongodb-community'" >> ~/.zshrc
```

To access mongo db you can use either shell client or gui client.
Recommended free Gui client is [Robot 3T](https://robomongo.org/download) 






