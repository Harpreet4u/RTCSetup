# RTCSetup
Steps to setup RTC servers (signalling, STUN and TURN)

Basic steps to setup coturn as TURN server:

1. Install Dependencies
sudo apt-get install libssl-dev libevent-dev libhiredis-dev make -y

2. Download TURN server package
wget http://turnserver.open-sys.org/downloads/v4.5.0.6/turnserver-4.5.0.6.tar.gz

3. Create TURN user and password
sudo turnadmin -a -u happy -p happy

4. Run TURN server

sudo turnserver -L <listening-ip> -a -f
