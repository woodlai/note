```
name: cloudflare_ssh

on:
  push:
    branches:
      - master

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Install cloudflared
        run: |
          curl -L --output ./cloudflared.deb https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
          sudo dpkg -i ./cloudflared.deb
          cloudflared --version

      - name: Setup SSH
        uses: webfactory/ssh-agent@v0.9.0
        with:
          ssh-private-key: ${{ secrets.UBUNTU }}

      # - name: Add server to known hosts
      #   run: |
      #     ssh-keyscan -H -v ${{ vars.HOST }} >> ~/.ssh/known_hosts

      - name: Execute remote command
        env:
          CMD: '"cd /sources; test -d ./dnspod-shell-master&& ls -l ./dnspod-shell-master||echo "Directory not found""'
        run: ssh -p 22 -o StrictHostKeyChecking=no -o ProxyCommand="/usr/local/bin/cloudflared access ssh --hostname %h" ${{ vars.USER }}@${{ vars.HOST }} ${{env.CMD}}
```
