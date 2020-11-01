# autharmor-ssh
Auth Armor 2FA authentication SSH plugin

## Warning

You should have an alternative means of accessing your server in the event that you are unable to approve your Auth Armor 2FA requests such as a physical, graphical, or virtual TTY.

## Install

Requirements: `curl`, `awk`, `jq`, `uuidgen`

```shell
git clone https://github.com/devhen/autharmor-ssh.git
cd autharmor-ssh
sudo cp autharmor-ssh /usr/bin/
sudo chmod +x /usr/bin/autharmor-ssh
sudo cp autharmor-ssh.conf /etc/
echo "ForceCommand /usr/bin/autharmor-ssh" | sudo tee -a /etc/ssh/sshd_config
sudo systemctl reload sshd
```

Use the [Auth Armor dashboard](https://dashboard.autharmor.com) to generate API keys and register users.

Once your user(s) have been setup, place your Auth Armor API `CLIENT_ID` and `CLIENT_SECRET` in `/etc/autharmor-ssh`. The plugin will not enforce 2FA unless these keys have been set.
