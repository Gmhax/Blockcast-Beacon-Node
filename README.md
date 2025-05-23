# Blockcast-Beacon-Node
Blockcast is a decentralized content delivery network (CDN) and marketplace that helps broadcasters increase traffic and reach wider audiences. Blockcast bridges the gap between television and online streaming by tokenizing unused TV spectrum to deliver content.

![image](https://github.com/user-attachments/assets/3bf223d5-8af7-4fad-a708-ede119416564)



# 🛰️ Blockcast Beacon Node Installation Guide

A step-by-step guide to install and register a Blockcast beacon node on Ubuntu/Linux.

---

## 📌 Prerequisites

1. **Register an Account**
   - Sign up at [https://app.blockcast.network?referral-code=0oP2QK](https://app.blockcast.network)

2. **Create and Link a Wallet**
   - Use [Phantom](https://phantom.app) or [Solflare](https://solflare.com) to create a wallet.
   - Go to the **"Profile"** section on the Blockcast site and **connect your wallet**.
   > ⚠️ Required to link a wallet before adding a node!

---

## 🖥️ Node Installation (Ubuntu/Linux)

### Step 1: Update Packages and Install Git
```bash
sudo apt update && sudo apt install git -y
```

### Step 2: Install Docker (if not already installed)
```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] \
https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install docker-ce -y
sudo systemctl restart docker
sudo systemctl status docker
```

### Step 3: Download Blockcast Node Files
```bash
git clone https://github.com/Blockcast/beacon-docker-compose.git
```

### Step 4: Navigate Into the Node Directory
```bash
cd beacon-docker-compose
```

### Step 5: Start the Node
```bash
docker compose up -d
```

### Step 6: Verify Running Containers
- Make sure the following containers are running:
- control_proxy
- beacond
- blockcastd

```bash
docker ps
```

### Step 7: Generate Node Keys
- Save the generated Hardware ID and Challenge Key. These will be used to register your node.
```bash
docker compose exec blockcastd blockcastd init
```

### Node Registration
### Step 8: Register Your Node
- Go to https://app.blockcast.network
- Click "Get A Node"
### Input:

- Hardware ID (from Step 7)
- Challenge Key (from Step 7)
- Node Name (custom)
- Location (your server's physical location)
- Click "Register Node"

✅ Done!
- Check your node status on the dashboard. Make sure it shows online and synced.
































