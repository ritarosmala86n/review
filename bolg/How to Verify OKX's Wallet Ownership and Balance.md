
# How to Verify OKX's Wallet Ownership and Balance

This guide explains the steps to verify OKX's ownership and the balance of its wallet addresses using the OKX reserve snapshot file and an open-source reserve verification tool.

---

## Preparation Before Verification

1. **Download the Verification Tool**  
   Open the [verification tool](https://github.com/okx/proof-of-reserves/releases/tag/v3.0.4), select the ZIP file to download. The folder contains two key tools:
   - **VerifyAddress**: Used to verify ownership of reserve addresses.
   - **CheckBalance**: Used to verify reserve address balances. *(Note: `rpc.json` needs to be configured with node RPC or OKLink open API information.)*

   ![Folder Contents](https://www.okx.com/cdn/assets/plugins/announcements/contentful/tofttmniq0qv/5LVsZwGFGlfh5OZevkgtMO/f825f1e5fc451dfa5f06dcf7fd7cd13d/folder.PNG)

2. **Download the Audit Files**  
   Access the [OKX audit files](https://www.okx.com/en-us/proof-of-reserves/download) and download the proof of reserves data.

3. **Organize Files**  
   Place the downloaded proof of reserves file and verification tool in the same folder.

---

## Verifying OKX's Ownership of Wallet Reserves

### Ownership Verification Steps

- **BTC Wallet**: OKX uses two signature methods for BTC addresses:
  - **Single-Signature Address**: Ownership is proven through the provided messages and signatures.
  - **Multi-Signature Address**: Uses a 2/3 signature method. Ownership is verified by confirming that OKX holds at least two private keys.

- **ETH & USDT Wallets**: Ownership is validated through the provided messages and signature results.

You can confirm the ownership of OKX's reserve addresses using the provided open-source or third-party tools.

---

### Using the Verification Tool

1. **Open the Terminal**  
   - For Mac: Use **Terminal**.  
   - For Windows: Use **Command Prompt**.

2. **Navigate to the Tool Directory**  
   Run the command:  
   ```bash
   cd ~/Downloads/proof-of-reserves
   ```

3. **Run the Verification Command**  
   For example:
   - Mac:  
     ```bash
     ./VerifyAddress --por_csv_filename=okx_por_20221122.csv
     ```
   - Windows:  
     ```cmd
     VerifyAddress.exe --por_csv_filename=okx_por_20221122.csv
     ```
   - *Note*: If Mac users encounter a developer verification issue, adjust the settings in **System Preferences** > **Security & Privacy**.

4. **Verification Result**  
   If successful, the terminal will display:  
   `"Verify address signature end, all address passed."`

---

### Verifying Ownership via Third-Party Tools

1. **Download Audit Files**  
   Download the [audit files](https://www.okx.com/en-us/proof-of-reserves/download).

2. **Copy Address Records**  
   Select an address, message, and signature from the file.

   ![Copy Address Record](https://www.okx.com/cdn/assets/plugins/announcements/contentful/tofttmniq0qv/5GQ7ZzFxBgw4Vo4DdR8TXy/d2560c1b249b90ccbb4cb290d6c05ba7/CT-web-POR-copy_record.png)

3. **Use a BTC Verification Tool**  
   Go to the [BTC signature verification tool](https://www.bitcoin.com/tools/verify-message/) and paste the address, message, and signature.

4. **Result Verification**  
   The tool will confirm whether the address is valid.

---

## Advertorial Content

🚀 Unlock Your Crypto Journey with OKX! Trade with zero fees, access cutting-edge Web3 features, and join millions of global traders. New users get an exclusive welcome bonus of up to 100 USDT! Start your trading adventure today with the world's leading digital asset platform.

[Click to view ☞ OKX Welcome Limited-Time Offer, Claim Up to 100 USDT Reward](https://bit.ly/OKXe)

---

## Verifying Reserve Balances

To ensure transparency, OKX provides tools for verifying balances of specific addresses or total balances for supported crypto chains.

### BTC Address Balance Verification

1. **Install Bitcoin Core**  
   Download [Bitcoin Core](https://bitcoincore.org/en/download/) (v0.21 or above).

2. **Synchronize and Roll Back Node**  
   Roll back the node to the snapshot height to match OKX's reserve data.

3. **Use CheckBalance Tool**  
   - Example Command:  
     ```bash
     ./CheckBalance --mode="single_address" --coin_name="btc" --address="3A1JRKqfGGxoq2qSHLv85u4zn935VR9ToL" --por_csv_filename=okx_por_20221122.csv
     ```
   - The balance for the specified address will be displayed.

4. **Compare Results**  
   Match the on-chain balance with OKX's published data.

### Verifying ETH/USDT Balances

1. Use `CheckBalance` to verify Ethereum or USDT balances across supported chains (e.g., Ethereum, Arbitrum, Optimism).
2. Commands to verify single addresses or total balances are similar to the BTC commands above, replacing the coin name.

---

## Appendix: Using Third-Party RPC Nodes or APIs

- **Infura or Alchemy**: Use services like [Infura](https://www.infura.io/) or [Alchemy](https://www.alchemy.com/) to configure RPC parameters.
- **OKLink API**: OKLink provides an open API to query address balances at specific heights.

   Example Configuration:  
   ![Example Alchemy Configuration](https://www.okx.com/cdn/assets/plugins/announcements/contentful/tofttmniq0qv/7IWoKmj9ty5EtvhhrLan6S/c0abbf96e54c775ccec9eec3a4f831d6/CT-web-POR-example_of_alchemy.png)

---

By following these steps, you can confidently verify OKX's wallet ownership and balances. Start your verification journey today and ensure complete transparency with OKX!
