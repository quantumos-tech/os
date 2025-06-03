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
cargo build --release

```

## Development Tools

Chain Spec

```
cargo install staging-chain-spec-builder

chain-spec-builder create \
  --relay-chain "rococo-local" \
  --para-id 1000 \
  --runtime target/release/wbuild/parachain-template-runtime/parachain_template_runtime.wasm \
  named-preset development

```

Run Locally with Omni Node

```
cargo install polkadot-omni-node
polkadot-omni-node --chain path/to/chain_spec.json --dev

```