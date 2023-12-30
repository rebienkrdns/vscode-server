## Installation
```bash
curl -Lk 'https://code.visualstudio.com/sha/download?build=stable&os=cli-alpine-x64' --output vscode_cli.tar.gz

tar -xf vscode_cli.tar.gz
```

## Init
```bash
./code tunnel
```

## Remember url generated on Init step
[vscode-server](https://vscode.dev/tunnel/vscode-server)

## AutoStartup configuration

```bash
sudo nano /etc/systemd/system/vscode-server.service
```

```service
[Unit]
Description=vscode-server

[Service]
ExecStart=/home/ubuntu/code tunnel
Restart=always
User=ubuntu
Group=ubuntu

[Install]
WantedBy=default.target
```

```bash
sudo systemctl enable vscode-server.service
sudo systemctl start vscode-server.service
sudo systemctl status vscode-server.service
```

