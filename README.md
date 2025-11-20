# 🚀 **Pumpfun Bundler**

The **Pumpfun Bundler** is a fast and efficient self-bundling script for **PumpFun**, enabling you to create a token and execute multiple buys in a single bundle.
Previously, we supported **25 wallets**, but due to the latest Pumpfun update, the maximum is now **13 wallets per bundle**.

Perfect for streamlined launches, fast volume creation, and smooth trading workflows.

---

## ✨ **Features**

* 🪙 **Create Tokens Instantly:** Launch your custom token with a single script.
* 🤝 **13 Buyers in One Bundle:** Execute simultaneous purchases using multiple wallets.
* ⚡ **Fast & Reliable:** Optimized for speed and accurate transaction execution.
* 🔍 **Transparent Tracking:** Verify all actions directly on Solscan.

---

## 📜 **Working History**

* [https://solscan.io/token/3GX98sHYV1ry5uUQD9zMFn75K9NRm541ZmEzDbTun6UC](https://solscan.io/token/3GX98sHYV1ry5uUQD9zMFn75K9NRm541ZmEzDbTun6UC)

---

## 🛠 **Installation**

Install the PumpFun SDK:

```bash
npm i pumpdotfun-sdk
```

---

## 📋 **Usage**

### **Step 1: Configure Environment**

1️⃣ Create a `.env` file using `.env.example` as a reference.
2️⃣ Add your **RPC URL**.

---

### **Step 2: Fund the Account**

💸 Ensure the generated account has **at least 0.004 SOL**.

---

### **Step 3: Customize Token Metadata**

```ts
const metadata = {
  name: "g0drlc",
  symbol: "G0DRLC",
  description: "this is g0drlc token",
  image: "./upload/img.jpg",
  showName: true,
  createdOn: "https://pump.fun",
  twitter: "https://x.com/x80drlc",
  telegram: "https://t.me/g0drlc",
  website: "https://alie"
};
```

---

### **Step 4: Run the Script**

```bash
npx ts-node example/basic/index.ts
```

---

### **Step 5: Verify Your Token**

Use trusted Solana tools:

* **PumpFun:** [https://pump.fun/tokenaddress](https://pump.fun/tokenaddress)
* **Solscan:** [https://solscan.io](https://solscan.io)

---

## 🔧 **SDK Methods**

### **`createAndBuy` — Create a token + buy it**

```ts
async createAndBuy(
  creator: Keypair,
  mint: Keypair,
  createTokenMetadata: CreateTokenMetadata,
  buyAmountSol: bigint,
  slippageBasisPoints: bigint = 500n,
  priorityFees?: PriorityFee,
  commitment: Commitment = DEFAULT_COMMITMENT,
  finality: Finality = DEFAULT_FINALITY
): Promise<TransactionResult>
```

---

### **`buy` — Buy tokens**

```ts
async buy(
  buyer: Keypair,
  mint: PublicKey,
  buyAmountSol: bigint,
  slippageBasisPoints: bigint = 500n,
  priorityFees?: PriorityFee,
  commitment: Commitment = DEFAULT_COMMITMENT,
  finality: Finality = DEFAULT_FINALITY
): Promise<TransactionResult>
```

---

### **`sell` — Sell tokens**

```ts
async sell(
  seller: Keypair,
  mint: PublicKey,
  sellTokenAmount: bigint,
  slippageBasisPoints: bigint = 500n,
  priorityFees?: PriorityFee,
  commitment: Commitment = DEFAULT_COMMITMENT,
  finality: Finality = DEFAULT_FINALITY
): Promise<TransactionResult>
```

---

## 📡 **Event Listener Example**

```ts
sdk.addEventListener("tradeEvent", (event, slot, signature) => {
  console.log("Trade Event:", event, slot, signature);
});
```

Run event listener:

```bash
npx ts-node example/events/events.ts
```

---

## 🤝 **Contributing**

Contributions are welcome!
Submit pull requests or open issues with suggestions.

---

## 🌟 **Get Started Today**

Need help with your bundler, Pumpfun automation, or custom bots?
Contact me on **Telegram:** [@g0drlc](https://t.me/g0drlc)
