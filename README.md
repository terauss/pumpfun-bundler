

# 🚀 **Pumpfun Bundler**  

The **Pumpfun Bundler** is the fastest, most efficient self-bundling script for **PumpFun**, enabling you to create a token and execute purchases with **25 buyers in a single bundle**. Perfect for streamlined launches and trading efficiency!  

---

## ✨ **Features**  

- 🪙 **Create Tokens Instantly:** Launch your custom token with ease.  
- 🤝 **25 Buyers in One Bundle:** Simultaneously manage multiple purchases.  
- ⚡ **Fast and Reliable:** Designed for speed and transaction accuracy.  
- 🔍 **Transparent Tracking:** Validate transactions directly on Solscan.  

---

## 🛠 **Installation**  

Install the PumpFun SDK with a single command:  

```bash
npm i pumpdotfun-sdk
```  

---

## 📋 **Usage**  

### **Step 1: Configure Environment**  
1️⃣ Create a `.env` file using `.env.example` as a reference.  
2️⃣ Add your **RPC URL** to the `.env` file.  

### **Step 2: Fund the Account**  
💸 **Fund Alert:** Ensure the account generated in the next step has **at least 0.004 SOL**.  

### **Step 3: Customize Token Metadata**  
Edit the metadata to define your token's properties:  

```typescript
const metadata = {
  "name": "Alie",
  "symbol": "AAA",
  "description": "AAA token",
  "image": "./upload/img.jpg",
  "showName": true,
  "createdOn": "https://pump.fun",
  "twitter": "https://x.com/alie",
  "telegram": "https://t.me/alie",
  "website": "https://alie"
};
```

### **Step 4: Run the Script**  
🚀 Execute the script to launch your token and perform bundling:  

```bash
npx ts-node example/basic/index.ts
```

### **Step 5: Verify Your Token**  
🔗 Use these tools to check your token launch and bundling status:  
- [**PumpFun**](https://pump.fun/tokenaddress)  
- [**Solscan.io**](https://solscan.io)  

---

## 🔧 **SDK Methods**  

### **`createAndBuy`**  
💡 **Purpose:** Creates a token and buys it.  
📜 **Method Signature:**  

```typescript
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

- **Parameters:**  
  - 🔑 `creator`: Creator's keypair.  
  - 🔑 `mint`: Mint account keypair.  
  - 📝 `createTokenMetadata`: Metadata for the token.  
  - 💰 `buyAmountSol`: Amount of SOL to buy.  
  - 📉 `slippageBasisPoints`: Slippage (default: 500).  

---

### **`buy`**  
💡 **Purpose:** Buy a specified amount of tokens.  
📜 **Method Signature:**  

```typescript
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

### **`sell`**  
💡 **Purpose:** Sell a specified amount of tokens.  
📜 **Method Signature:**  

```typescript
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

### **Subscribe to Events**  

Easily set up event listeners to monitor your token's lifecycle:  

```typescript
sdk.addEventListener("tradeEvent", (event, slot, signature) => {
  console.log("Trade Event:", event, slot, signature);
});
```

### **Run Event Script**  

```bash
npx ts-node example/events/events.ts
```

---

## 🤝 **Contributing**  

We welcome contributions! 💡 Submit a pull request or open an issue to share your ideas.  

---

## 🌟 **Get Started Today!**  

🌐 Start your **Pumpfun Bundler** journey now!  
🔗 If you need help, contact me on telegram **[@g0rlc](https://t.me/g0drlc)** to explore more.  
