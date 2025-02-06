#  Liquidity Pallet for Substrate

This repository provides a **Liquidity Pallet** that allows users to manage assets and liquidity on a **Substrate-based blockchain**.

##  Features

✅ **Liquidity Management**: Deposit and withdraw liquidity  
✅ **Asset Management**: Create and transfer assets  
✅ **Custom Pallet Integration** for Substrate Runtime  

---

##  **Installation & Setup**

### 1️ **Clone the Repository**
```sh
git clone https://github.com/your-repo/liquidity-pallet.git
cd liquidity-pallet
```

### 2️⃣ **Add Liquidity Pallet to Your Substrate Runtime**
Modify the `runtime/src/lib.rs` file to include the **Liquidity Pallet**:

```rust
parameter_types! {
    pub const LiquidPalletId: PalletId = PalletId(*b"liq/pllt");
}

impl pallet_liquidity::Config for Runtime {
    type RuntimeEvent = RuntimeEvent;
    type Currency = Balances;
    type PalletId = LiquidPalletId;
}
```

### 3️⃣ **Update Cargo.toml**
Ensure your `Cargo.toml` includes the Liquidity Pallet:

```toml
[dependencies]
pallet-liquidity = { path = "../pallets/liquidity" }
```

Then, update the **runtime Cargo.toml**:

```toml
[features]
default = ["pallet-liquidity"]
```

### 4️⃣ **Build & Compile the Node**
```sh
cargo build --release
```

### 5️⃣ **Run the Substrate Node**
```sh
./target/release/substrate-node --dev
```

---

## 🔗 **Usage**
Once your Substrate node is running, interact with it using **Polkadot.js Apps** or **custom scripts**.

---

## ❓ **Troubleshooting & FAQs**
### ❌ **Compilation Error?**
👉 Ensure your **Rust toolchain** is up-to-date:
```sh
rustup update
```

### ❌ **Substrate Node Crashing?**
👉 Run with more logging:
```sh
RUST_LOG=debug ./target/release/substrate-node --dev
```

---

## 📜 **License**
This project is licensed under **Apache 2.0**.
