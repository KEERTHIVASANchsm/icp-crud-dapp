# 🌐 ICP CRUD dApp — Internet Computer Protocol

A full-stack decentralised application built on the **Internet Computer Protocol (ICP)**, implementing complete CRUD operations with a **Rust backend canister** and a **React frontend** — both deployed entirely on-chain with no traditional cloud infrastructure.

---

## 🧠 What Makes This Different

Most "decentralised" apps host their frontend on AWS or Vercel and only put transactions on-chain. This project goes further — both the backend logic **and** the frontend run as ICP canisters, making the entire application truly decentralised.

---

## 🏗 Architecture

```
┌─────────────────────────────────────┐
│         React Frontend              │
│    (deployed as ICP asset canister) │
└────────────────┬────────────────────┘
                 │  Candid interface calls
┌────────────────▼────────────────────┐
│         Rust Backend Canister       │
│                                     │
│  create_record()                    │
│  read_record(id)                    │
│  update_record(id, data)            │
│  delete_record(id)                  │
│  list_all_records()                 │
└─────────────────────────────────────┘
```

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| **Backend** | Rust (ICP canister) |
| **Frontend** | React + JavaScript |
| **Interface** | Candid (ICP's interface description language) |
| **Network** | Internet Computer Protocol |
| **Local Dev** | DFX SDK |

---

## 🚀 Running Locally

### Prerequisites
- [DFX SDK](https://internetcomputer.org/docs/current/developer-docs/setup/install) installed
- Node.js 16+
- Rust toolchain

```bash
cd icp_crud_dapp/

# Start local ICP replica in background
dfx start --background

# Deploy canisters and generate Candid interface
dfx deploy
```

Your app will be available at:
```
http://localhost:4943?canisterId={asset_canister_id}
```

### Frontend Development

```bash
# Regenerate Candid interface after backend changes
npm run generate

# Start frontend dev server (proxies to replica at port 4943)
npm start
# → http://localhost:8080
```

### Useful Commands

```bash
dfx help
dfx canister --help
```

---

## 📚 Learning Resources

- [Quick Start — Deploy Locally](https://internetcomputer.org/docs/current/developer-docs/setup/deploy-locally)
- [Rust Canister Development Guide](https://internetcomputer.org/docs/current/developer-docs/backend/rust/)
- [ic-cdk docs](https://docs.rs/ic-cdk)
- [Candid Introduction](https://internetcomputer.org/docs/current/developer-docs/backend/candid/)

---

## 💡 What I Learned

- How **Candid** works as a language-agnostic interface between frontend and backend canisters
- Why **Rust's ownership model** suits canister development — memory safety without garbage collection
- The difference between ICP's **actor model** and Ethereum's account model
- How **on-chain frontend hosting** changes the trust assumptions of a dApp

---

## 📌 Context

Built during active involvement with the **ICP Hub community** and my blockchain internship at BlockseBlock (2025). Represents a shift from Ethereum-centric development toward exploring alternative L1 architectures.
