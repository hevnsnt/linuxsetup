# linuxsetup
Just some basic Linux things to get a new system setup the way I want it.


# Setup non-root user [as root]:
* adduser username
* usermod -aG sudo username

# Install MFA for user:
https://www.howtogeek.com/121650/how-to-secure-ssh-with-google-authenticators-two-factor-authentication/
* sudo apt-get install libpam-google-authenticator
* google-authenticator
* sudo nano /etc/pam.d/sshd and add "auth required pam_google_authenticator.so"
* nano etc/ssh/sshd_config and change: ChallengeResponseAuthentication yes
     also change port: add another port line with favority port
* sudo service ssh restart

# Setup SSH keys
ssh-copy-id user@SERVER_IP_ADDRESS

# python virtualenv
* pip install virtualenv
* pip install virtualenvwrapper
* export WORKON_HOME=~/Envs
* source /usr/local/bin/virtualenvwrapper.sh

## Usage:
* mkvirtualenv my_project
* workon my_project
* deactivate
* rmvirtualenv venv
