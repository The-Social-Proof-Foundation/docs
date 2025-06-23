---
icon: check
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Run a Validator

Operating a MySocial Validator Node allows you to participate in the network's consensus mechanism, validate transactions, and contribute to the blockchain's security and decentralization.

## Hardware Requirements

Ensure your system meets the following minimum specifications:

* **CPU**: 24 physical cores (or 48 virtual cores)
* **Memory**: 128 GB
* **Storage**: 4 TB NVMe SSD
* **Network**: 1 Gbps

## Software Requirements

MySocial recommends using a Linux system, preferably Ubuntu or Debian. However, you can also run a Validator Node on macOS for development purposes. Below are the instructions for both operating systems.

### Linux

```
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install -y --no-install-recommends \
  tzdata libprotobuf-dev ca-certificates build-essential \
  libssl-dev libclang-dev libpq-dev pkg-config openssl \
  protobuf-compiler git clang cmake
```

### macOS

Ensure you have [Homebrew](https://brew.sh/) installed. Then, install the required dependencies:

```
brew update
brew install protobuf openssl llvm cmake pkg-config
```

Set environment variables for OpenSSL and LLVM:

```
export PATH="/usr/local/opt/openssl@3/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/openssl@3/lib"
export CPPFLAGS="-I/usr/local/opt/openssl@3/include"
export PATH="/usr/local/opt/llvm/bin:$PATH"
export LDFLAGS="-L/usr/local/opt/llvm/lib"
export CPPFLAGS="-I/usr/local/opt/llvm/include"
```

## Install Rust

Install and update Rust:

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustup update stable
```

Verify the installation:

```
cargo --version
rustc --version
```

## Building and Installing MySocial Validator Node

Clone the MySocial repository and build the node:

```
git clone https://github.com/the-social-proof-foundation/mysocial-core.git
cd mysocial
git remote add upstream https://github.com/the-social-proof-foundation/mysocial-core
git fetch upstream
git checkout --track upstream/mainnet
cargo build --release -p mysocial-node -p mysocial
```

Move the binaries to /usr/local/bin:

```
sudo mv target/release/mysocial-node /usr/local/bin/
sudo mv target/release/mysocial /usr/local/bin/
```

## Configuring the Validator Node

Set up the configuration:

```
mkdir -p $HOME/.mysocial
cp crates/mysocial-config/data/validator-template.yaml $HOME/.mysocial/validator.yaml
curl -fLJO https://github.com/MySocialLabs/mysocial-genesis/raw/main/mainnet/genesis.blob -o $HOME/.mysocial/genesis.blob
```

Generate the necessary keys:

```
mysocial keytool generate bls12381
mysocial keytool generate ed25519
mysocial keytool generate ed25519
mysocial keytool generate ed25519
```

This will create key files in your current directory. Move them to your configuration directory:

```
mv *.key $HOME/.mysocial/
```

Edit validator.yaml to include the correct paths to your keys and other configurations:

```
protocol-key: "/home/your-username/.mysocial/protocol.key"
account-key: "/home/your-username/.mysocial/account.key"
network-key: "/home/your-username/.mysocial/network.key"
worker-key: "/home/your-username/.mysocial/worker.key"
db-path: "/home/your-username/.mysocial/db"
genesis:
  genesis-file-location: "/home/your-username/.mysocial/genesis.blob"
```

Replace /home/your-username with your actual home directory path.

## Running the Validator Node

### Linux

Create a systemd service file:

```
sudo tee /etc/systemd/system/mysocial-validator.service > /dev/null <<EOF
[Unit]
Description=MySocial Validator Node
After=network-online.target

[Service]
User=$USER
WorkingDirectory=$HOME/mysocial
ExecStart=/usr/local/bin/mysocial-node --config-path $HOME/.mysocial/validator.yaml
Restart=on-failure
RestartSec=3
LimitNOFILE=65535

[Install]
WantedBy=multi-user.target
EOF
```

Enable and start the service:

```
sudo systemctl enable mysocial-validator
sudo systemctl daemon-reload
sudo systemctl start mysocial-validator
```

Check the service status:

```
sudo systemctl status mysocial-validator
```

View logs:

```
journalctl -u mysocial-validator -f
```

### macOS

On macOS, you can run the validator node directly from the command line:

```
mysocial-node --config-path $HOME/.mysocial/validator.yaml
```

To keep the node running continuously, consider using a process manager like launchd or a third-party tool such as supervisors.

## Joining the Validator Network

To become an active validator, you need to stake a minimum amount of MySocial tokens. Ensure your wallet has the required tokens and follow the staking procedures as outlined in the MySocial documentation.

By following these steps, you’ll have a MySocial Validator Node up and running, actively participating in the network’s consensus and contributing to its security and performance. If you have any issues, please reach out to us on out [Telegram channel](https://t.me/mysocial_chain) and we will be happy to help.
