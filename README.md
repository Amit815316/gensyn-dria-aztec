# gensyn-dria-aztec
One liner command for gensyn, aztec and dria

GENSYN
```
bash -c 'sudo apt-get update && sudo apt-get upgrade -y && sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev -y && sudo apt-get install python3 python3-pip python3-venv python3-dev -y && sudo apt-get update && curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash - && sudo apt-get install -y nodejs && sudo npm install -g yarn && curl -o- -L https://yarnpkg.com/install.sh | bash && export PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH" && source ~/.bashrc && node -v && yarn -v && npm -v && python3 --version && git clone https://github.com/gensyn-ai/rl-swarm/ && cd rl-swarm && screen -S gensyn bash -c "python3 -m venv .venv && source .venv/bin/activate && pip install --force-reinstall transformers==4.51.3 trl==0.19.1 && pip freeze && exec bash"'
```
Move your old swarm file to vps by SFTP or use the bleow command directly if you are new user
```bash
./run_rl_swarm.sh
```
Install Localtunnel
```
npm install -g localtunnel
```
Get link for login
```
lt --port 3000
```


AZTEC
```
sudo apt-get update && sudo apt-get upgrade -y && curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt update && sudo apt install -y nodejs && sudo apt install -y curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev screen ufw apt-transport-https ca-certificates software-properties-common && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg && echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null && sudo apt update && sudo apt install -y docker-ce && sudo systemctl enable --now docker && sudo usermod -aG docker $USER && echo "✅ Added $USER to 'docker' group. Please log out and back in, or run: exec su -l $USER"
```
```
sudo curl -L "https://github.com/docker/compose/releases/download/$(curl -s https://api.github.com/repos/docker/compose/releases/latest | jq -r .tag_name)/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && sudo chmod +x /usr/local/bin/docker-compose && docker --version && docker-compose --version && bash -i <(curl -s https://install.aztec.network) && echo 'export PATH="$HOME/.aztec/bin:$PATH"' >> ~/.bashrc && source ~/.bashrc && aztec-up latest && sudo ufw allow 22 && sudo ufw allow ssh && sudo ufw allow 40400 && sudo ufw allow 8080 && sudo ufw --force enable && screen -S Aztec
```

make necessary changes
```
aztec start --node --archiver --sequencer \
  --network alpha-testnet \
  --l1-rpc-urls sepoliarpc \
  --l1-consensus-host-urls beaconrpc \
  --sequencer.validatorPrivateKeys privatekey \
  --sequencer.coinbase address \
  --p2p.p2pIp yourvpsip
```


DRIA
```
curl -fsSL https://ollama.com/install.sh | sh
```
```
curl -fsSL https://dria.co/launcher | bash

```
```
dkn-compute-launcher start
```
```
dkn-compute-launcher referrals
```
Get role - https://form.typeform.com/to/Eav42hR3?typeform-source=www.google.com
