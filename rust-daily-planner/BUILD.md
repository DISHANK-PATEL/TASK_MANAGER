# Building ICP Daily Planner Locally

This guide will help you build and deploy the ICP Daily Planner project locally for development and testing purposes.

## Prerequisites

Before you begin, make sure you have the following installed:

- [DFX SDK](https://internetcomputer.org/docs/building-apps/getting-started/installing-dfx)
- [Node.js](https://nodejs.org/en/download/package-manager)
- [Rust](https://doc.rust-lang.org/cargo/getting-started/installation.html#install-rust-and-cargo)
- [candid-extractor](https://crates.io/crates/candid-extractor)

### Installation Commands

1. Install `dfx`:
```bash
sh -ci "$(curl -fsSL https://internetcomputer.org/install.sh)"
```

2. Install Rust:
```bash
curl https://sh.rustup.rs -sSf | sh
```

3. Install candid-extractor:
```bash
cargo install candid-extractor
```

> **Note**: On Apple Silicon (e.g., Apple M1 chip), make sure you have Rosetta installed: `softwareupdate --install-rosetta`

## Development Setup

### Option 1: Native Development

1. Navigate to your project directory:
```bash
cd rust-daily-planner
```

2. Install dependencies:
```bash
npm install
```

### Option 2: Dev Containers (Recommended for Windows)

If you're on Windows or prefer containerized development:

1. Install the [Dev Container extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) for VS Code
2. Install [Docker](https://docs.docker.com/engine/install/)
3. Open the project in VS Code
4. Start the Dev Container by selecting `Dev-Containers: Reopen in Container` in VS Code's command palette (F1 or Ctrl/Cmd+Shift+P)

> **Note**: Local development ports (e.g., the ports used by `dfx` or `vite`) are forwarded from the Dev Container to your local machine. Use Ctrl/Cmd+Click on the displayed local URLs to open them in your browser.

## Create a Local Developer Identity

It's recommended to create a local [developer identity](https://internetcomputer.org/docs/building-apps/getting-started/identities) rather than use the default `dfx` identity.

1. Start the local replica:
```bash
dfx start --background
```

2. Create a new identity:
```bash
dfx identity new IDENTITY_NAME
```

3. Use the new identity:
```bash
dfx identity use IDENTITY_NAME
```

Replace `IDENTITY_NAME` with your preferred identity name. The `dfx identity new` command will return your identity's seed phrase - save this in a secure location.

## Deploy Locally

1. Deploy your project to the local environment:
```bash
dfx deploy
```

2. Your project will be hosted locally. The canister URLs will be shown in the terminal output.

3. Open the URLs in your web browser to view your local ICP Daily Planner.

## Deploy to Mainnet

To deploy your project to the mainnet for public access:

### 1. Obtain Cycles

You'll need [cycles](https://internetcomputer.org/docs/building-apps/getting-started/tokens-and-cycles) to pay for mainnet resources. Convert ICP tokens to cycles:

```bash
dfx cycles convert AMOUNT --network ic
```

Replace `AMOUNT` with the number of ICP tokens you want to convert.

### 2. Deploy to Mainnet

```bash
dfx deploy --network ic
```

### 3. Manage Cycles

After deployment, your project will continuously require cycles. You can:

- [Top up canisters manually](https://internetcomputer.org/docs/building-apps/canister-management/topping-up)
- Set up automatic cycles management through [CycleOps](https://cycleops.dev/)

> **Important**: If your canisters run out of cycles, they will be removed from the network.

## Development Workflow

1. Make changes to your code
2. Deploy locally: `dfx deploy`
3. Test your changes
4. When ready, deploy to mainnet: `dfx deploy --network ic`

## Additional Resources

- [ICP Documentation](https://internetcomputer.org/docs)
- [DFINITY Examples Repository](https://github.com/dfinity/examples)
- [ICP Developer Forum](https://forum.dfinity.org/)
