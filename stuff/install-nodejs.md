## Install NodeJS
- New versions of Node aren't directly `apt`able
---
```shell
sudo apt install -y curl
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt install -y nodejs
```
or, change the 16 (for Node 16.x) to a greater value