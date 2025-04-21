<div align="center">

# 💻 Gensyn AI RL-Swarm Guide (Windows/Mac/Linux) 💻

</div>

## ✅ System Requirements
![image](https://github.com/user-attachments/assets/c82d8c07-2880-4d3b-be39-1655fc7c95ab)

> ❌ **Don’t use low-spec devices!** It may crash your system.

Use a good VPS or high-performance local machine.



## NOTE: You Can rent VPS on "https://contabo.com/en/vps/" budget freindly 

 
## 1️⃣ Connect to VPS

```bash
ssh username@ip
```

## 2️⃣ Install Python & Tools

### 🔧 Linux/Wsl:

```bash
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof
```

### 🍏 Mac:

```bash
brew install python
```

Check Python version:

```bash
python3 --version
```

## 3️⃣ Install Node.js & Yarn

### 🔧 Linux/Wsl:

```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt install -y nodejs
```

Install Yarn:

```bash
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list > /dev/null
sudo apt update && sudo apt install -y yarn
```

### 🍏 Mac:

```bash
brew install node && corepack enable && npm install -g yarn
```

Check versions:

```bash
node -v
npm -v
yarn -v
```

## 🚀 Start the RL Swarm Node

```bash
git clone https://github.com/gensyn-ai/rl-swarm.git
screen -S gensyn
cd rl-swarm
python3 -m venv .venv
source .venv/bin/activate
cd modal-login
yarn install
yarn upgrade && yarn add next@latest && yarn add viem@latest
cd ..
./run_rl_swarm.sh
```

When prompted:
- `Y` to connect to testnet.
- Login via popup or http://localhost:3000/
- Save your ORG_ID
- `N` for Hugging Face

Logs will start showing.

Detach screen: `Ctrl + A`, then `D`  
To reattach: `screen -r gensyn`

### 💾 Save Chat Bonus Files

To resume and claim chat bonuses or rewards in the future, make sure to back up these files:

- `swarm.pem` → Located in the root of `rl-swarm` folder
- `userApiKey.json` and `userData.json` → Located in `modal-login/temp-data/`

You can copy them to a safe location on your device or cloud.

📌 Example command to copy from VPS to local:

```bash
scp USERNAME@YOUR_IP:~/rl-swarm/swarm.pem ~/swarm.pem
scp USERNAME@YOUR_IP:~/rl-swarm/modal-login/temp-data/userApiKey.json ~/
scp USERNAME@YOUR_IP:~/rl-swarm/modal-login/temp-data/userData.json ~/

