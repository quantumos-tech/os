# Component-Level Architecture
```
+===========================================================+
|                    QuantumOS Blockchain                   |
|               (Substrate Runtime with Custom Pallets)     |
|-----------------------------------------------------------|
| - pallet-task: Task creation, assignment, reward logic    |
| - pallet-verifier: ZKP & result validation                |
| - pallet-balances / staking / governance                  |
+============================▲==============================+
                             |
              Submit result + proof (tx)
                             |
+============================|==============================+
|                     Miner Node (Rust Daemon)              |
|-----------------------------------------------------------|
| [ TaskFetcher ] <--- JSON-RPC / Subxt ---> Chain API      |
| [ PhysicsEngine ]: Runs simulation (e.g., spin model)     |
| [ ZK-Prover ]: Generates SNARK/STARK proof of work        |
| [ IPFSUploader ]: Uploads raw result to IPFS/Filecoin     |
| [ Submitter ]: Sends CID + ZKP to chain                   |
+============================|==============================+
                             |
                             v
+===========================================================+
|        Off-chain Storage (IPFS / Filecoin integration)    |
| - Store simulation outputs (data, logs, models, etc.)     |
| - Referenced by CID in blockchain state                   |
+===========================================================+

                             ▲
                             |
                             v

+========================= QuantumOS dApp ==========================+
| - Web UI to browse, create, and verify simulation tasks           |
| - Connect wallet (Polkadot.js, Talisman, etc.)                   |
| - Display CID-linked results + proof status                      |
| - Explorer, Miner leaderboard, staking, governance               |
+==================================================================+

```
## Key Components
- Component	Description
- pallet-task	On-chain logic to define simulation tasks
- pallet-verifier	Verifies result + attached ZKP
- PhysicsEngine	Runs simulation workload (off-chain)
- ZK-Prover	Generates zero-knowledge proof of correctness
- IPFSUploader	Stores result data to decentralized storage
- dApp	Web-based frontend to interact with the chain
