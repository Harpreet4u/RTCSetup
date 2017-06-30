# RTCSetup
Steps to setup RTC servers (signalling, STUN, TURN and Media servers)

Basic steps to setup coturn as TURN server:

1. Install Dependencies
```
sudo apt-get install libssl-dev libevent-dev libhiredis-dev make -y
```

2. Download TURN server package
``` 
wget http://turnserver.open-sys.org/downloads/v4.5.0.6/turnserver-4.5.0.6.tar.gz
```

3. Install turn server

```
$ tar xvfz turnserver-2.6.5.2.tar.gz
$ cd turnserver-2.6.5.2
$ ./configure
$ make
$ sudo make install
$ ldconfig
```

4. Create TURN user and password
``` 
sudo turnadmin -a -u happy -p happy
```

5. Open all relevent ports

6. Running TURN server:
```
sudo turnserver -L <listening-ip> -a -f
```

For AWS (or write params in config file):
``` 
sudo turnserver –syslog -a -L ‘amazon ec2 PRIVATE ip address’ -X ‘amazon ec2 PUBLIC ip address’ -E ‘amazon ec2 PRIVATE ip address’ -f –min-port=32355 –max-port=65535 –user=’my_username’:’my_password’ -r realm –log-file=stdout -v
```

# Turn Config file setup:

1. Copy default config and edit all changes.
``` 
cp /usr/local/etc/turnserver.conf.default /usr/local/etc/turnserver.conf
```

> Uncomment `no-stun` in config file for turn only server. 

