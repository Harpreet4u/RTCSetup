# RTCSetup
Steps to setup RTC servers (signalling, STUN and TURN)

Basic steps to setup coturn as TURN server:

1. Install Dependencies
> sudo apt-get install libssl-dev libevent-dev libhiredis-dev make -y

2. Download TURN server package
> wget http://turnserver.open-sys.org/downloads/v4.5.0.6/turnserver-4.5.0.6.tar.gz

3. Install turn server

```
$ tar xvfz turnserver-2.6.5.2.tar.gz
$ cd turnserver-2.6.5.2
$ ./configure
$ make
$ sudo make install
```

4. Create TURN user and password
> sudo turnadmin -a -u happy -p happy

5. Run TURN server
> sudo turnserver -L <listening-ip> -a -f
