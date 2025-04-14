# ECLIPSE-POW
## 🔧 System Preparation

### 1. **Update & Upgrade Packages**
```bash
sudo apt-get update && sudo apt-get upgrade -y
```

### 2. **Install Required Utilities**
```bash
sudo apt install screen curl nano -y
```

---

## 🦀 Install Rust
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

---

## 🌞 Install Solana CLI
```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```

### Add Solana to PATH
```bash
echo 'export PATH="$HOME/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### Check Solana Version
```bash
solana --version
```

---

## 🔐 Create & Export Solana Wallet

### Create a New Wallet
```bash
solana-keygen new
```

### Get Wallet Config & Private Key Path
```bash
solana config get
cat ~/.config/solana/id.json
```

> 📥 Import this private key (`id.json`) into Backpack and fund your wallet.

---

## ⚙️ Install & Configure Bitz

### Install Bitz Miner
```bash
cargo install bitz
```

### Set RPC Endpoint
```bash
solana config set --url https://bitz-000.eclipserpc.xyz
```

---

## ⛏️ Start Mining

### Start a Screen Session
```bash
screen -S bitz
```

### Run the Miner (set cores according to your system)
```bash
bitz collect --cores 8
```

---

## 💰 Check & Claim Rewards

### Check Balance
```bash
bitz account
```

### Claim BITZ
```bash
bitz claim
```
