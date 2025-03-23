# Monitor of Solana Memecoin

## Features
- Real-time monitoring : subscribes to the Solana blockchain and listens for specific transaction logs.
- Token detection : identifies new tokens associated with a particular owner address.
- Customizable filters : easily modify the code to monitor different addresses or token criteria.
- Lightweight and efficient : built with asynchronous Rust for high performance.
- Robot sniper : automatically buys the token when it appears.

## Prerequisites
- Rust: Make sure you have Rust installed. If not, download it from https://www.rust-lang.org/
- Tokio Runtime: This project uses asynchronous programming, so the Tokio runtime is required.
- Solana Client Libraries: Uses solana_client and related crates.

## Installation
### 1. Install Dependencies

```shell
cargo build
```

## Usage

#### 1. Configure API Key Replace the placeholder API key in the code with your actual API key from https://dashboard.helius.dev/

```shell
let env = Env {
    ws_url: Url::parse(
        "wss://mainnet.helius-rpc.com/?api-key=YOUR_API_KEY",
    )?,
};
...
    let rpc_client = rpc_client::RpcClient::new(
     "https://mainnet.helius-rpc.com/?api-key=Your_API_KEY".to_string(),
 );
```

#### 2. Run the Program

```shell
cargo run
```
#### 3. Monitor Output

The application will begin monitoring and output messages when new tokens are detected.

## Key Componets

- PubsubClient: Used for subscribing to the Solana WebSocket for real-time updates.
- RpcClient: Allows fetching detailed transaction data from the Solana RPC API.
- Filters and Configs: Customized filters to narrow down the transactions of interest.
