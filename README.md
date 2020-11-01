# autharmor-ssh
AuthArmor 2FA authentication SSH plugin

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

Place your AuthArmor API `CLIENT_ID` and `CLIENT_SECRET` in `/etc/autharmor-ssh`.

Use the [AuthArmor Dashboard](https://dashboard.autharmor.com) to generate API keys add register users.

## Warning

You should have an alternative means of accessing your server in the event that you are unable to approve your AuthArmor 2FA requests such as a physical, graphical, or virtual TTY.