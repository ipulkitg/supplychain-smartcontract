# 🔐 Smart Contract for Asset Management on a Distributed Ledger (Go)

## 📘 Overview

This project demonstrates a basic **smart contract implementation in Go**, designed to interact with a decentralized ledger. It is a simplified simulation that introduces core smart contract principles such as **asset creation**, **ownership transfer**, and **state querying**. The focus is to showcase how **Go** can be used for writing smart contracts that could be integrated with blockchain systems like **Hyperledger Fabric**.

---

## 🧠 Key Features

- 🔐 **Create Asset** – Add new assets with a unique ID and owner
- 🔄 **Transfer Asset** – Change the ownership of an existing asset
- 📥 **Query Asset** – Retrieve asset details from the ledger
- ❌ **Delete Asset** – (Optional) Remove an asset for test/demo purposes
- 🧾 **State Ledger** – Mimics persistent storage of asset state using a key-value structure

---

## 🛠️ Technologies Used

- **Language**: Go (Golang)
- **Execution**: Local simulation or integration-ready for Hyperledger Fabric chaincode
- **Storage Abstraction**: In-memory or blockchain ledger store
- **Function Routing**: Entry-point handler dispatches calls to internal functions

---

## 🚀 How It Works

1. A client sends a transaction request to the smart contract
2. The contract checks the function name and routes it internally
3. Depending on the call, it will:
   - Create and store a new asset
   - Update the owner of an asset
   - Retrieve data associated with an asset ID
4. All transactions assume a simple key-value storage format (`map[string]string` style)

---

## 📊 Sample Functions (Defined in `smartcontract.go`)

```go
func CreateAsset(ctx contractapi.TransactionContextInterface, id string, owner string) error
func ReadAsset(ctx contractapi.TransactionContextInterface, id string) (string, error)
func TransferAsset(ctx contractapi.TransactionContextInterface, id string, newOwner string) error
func DeleteAsset(ctx contractapi.TransactionContextInterface, id string) error
```

Each function uses the `contractapi` interface to interact with the ledger, enabling plug-and-play usage within a real blockchain system like Hyperledger Fabric.

