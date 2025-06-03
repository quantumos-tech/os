# QuantumOS

QuantumOS is a decentralized blockchain protocol designed to simulate and verify real scientific computation tasks — especially quantum physics, gravitational fields, and spin dynamics — using a novel Proof of Useful Work (PoUW) mechanism.

---

## 🧠 What is QuantumOS?

- 🧩 **PoUW Protocol:** Nodes earn QOS tokens by completing verified simulations.
- 🧪 **Scientific Simulations:** Includes quantum spin systems, gravitational fields, and quantum chemistry.
- 🌐 **Decentralized Access:** Researchers and users submit jobs, miners compute, everyone earns.

---

## 🚀 Quick Start (Local Dev)

> Requires Rust + Cargo, plus Polkadot/Substrate toolchain.

```bash
# Install Rust
curl https://sh.rustup.rs -sSf | sh

# Clone repo
git clone https://github.com/quantumos-tech/os
cd os

# Build runtime
cargo build

```

After you build the project, you can use the following command to explore its parameters and subcommands:


```
./target/debug/quantumos-node  -h

```

## Single-Node Development Chain

The following command starts a single-node development chain that doesn't persist state:

```
./target/debug/quantumos-node  --dev

```

To purge the development chain's state, run the following command:

```
./target/debug/quantumos-node  purge-chain --dev

```

To start the development chain with detailed logging, run the following command:


```
RUST_BACKTRACE=1 ./target/debug/quantumos-node -ldebug --dev
Development chains:
```



