---
icon: cube
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

# Run a Full Node

Operating a MySocial Full Node enables you to validate blockchain activities, contributing to the network's security and decentralization.

If you haven't already, you need to [install MySocial CLI](../developer-tools/cli.md) on your system.

## Hardware Requirements

Ensure your system meets these minimum specifications:

* **CPU**: 8 physical cores / 16 virtual CPUs
* **RAM**: 128 GB
* **Storage**: 4 TB NVMe SSD

## Software Requirements

MySocial recommends using a Linux system, preferably Ubuntu or Debian. However, you can also run a Full Node on macOS for development purposes. Below are the instructions for both operating systems.

### Linux

Update your system and install necessary dependencies:

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

#### Install Rust

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

## Building and Installing MySocial Full Node

Clone the MySocial repository and build the node:

```
git clone https://github.com/the-social-proof-foundation/mysocial-core.git
cd mysocial-core
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

### Configuring the Full Node

Set up the configuration:

```
mkdir -p $HOME/.mysocial
cp crates/mysocial-config/data/fullnode-template.yaml $HOME/.mysocial/fullnode.yaml
curl -fLJO https://github.com/the-social-proof-foundation/mysocial-genesis/raw/main/mainnet/genesis.blob -o $HOME/.mysocial/genesis.blob
```

Edit fullnode.yaml to include peer nodes for state synchronization:

```
p2p-config:
  seed-peers:
    - address: /dns/mel-00.mainnet.mysocial.io/udp/8084
      peer-id: d32b55bdf1737ec415df8c88b3bf91e194b59ee3127e3f38ea46fd88ba2e7849
    - address: /dns/ewr-00.mainnet.mysocial.io/udp/8084
      peer-id: c7bf6cb93ca8fdda655c47ebb85ace28e6931464564332bf63e27e90199c50ee
    - address: /dns/ewr-01.mainnet.mysocial.io/udp/8084
      peer-id: 3227f8a05f0faa1a197c075d31135a366a1c6f3d4872cb8af66c14dea3e0eb66
    - address: /dns/lhr-00.mainnet.mysocial.io/udp/8084
      peer-id: c619a5e0f8f36eac45118c1f8bda28f0f508e2839042781f1d4a9818043f732c
```

Ensure db-path and genesis-file-location point to the correct locations:

```
db-path: "/home/your-username/.mysocial/db"
genesis:
  genesis-file-location: "/home/your-username/.mysocial/genesis.blob"
```

Replace /home/your-username with your actual home directory path.

### Running the Full Node

Create a systemd service file (Linux only):

```
sudo tee /etc/systemd/system/mysocial-node.service > /dev/null <<EOF
[Unit]
Description=MySocial Node
After=network-online.target

[Service]
User=$USER
WorkingDirectory=$HOME/mysocial
ExecStart=/usr/local/bin/mysocial-node --config-path $HOME/.mysocial/fullnode.yaml
Restart=on-failure
RestartSec=3
LimitNOFILE=65535

[Install]
WantedBy=multi-user.target
EOF
```

Enable and start the service (Linux only):

```
sudo systemctl enable mysocial-node
sudo systemctl daemon-reload
sudo systemctl start mysocial-node
```

For macOS, run the node directly:

```
mysocial-node --config-path $HOME/.mysocial/fullnode.yaml
```

Check the service status (Linux):

```
sudo systemctl status mysocial-node
```

View logs:

```
journalctl -u mysocial-node -f
```

By following these steps, you’ll have a MySocial Full Node up and running, contributing to the network’s integrity and performance.
