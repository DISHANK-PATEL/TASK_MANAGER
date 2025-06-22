# ICP Daily Planner

A modern daily planner built on the Internet Computer Protocol (ICP) featuring a monthly calendar for tracking daily activities, appointments, and tasks. All data is stored on-chain securely. For each day, historical facts can be queried using HTTPS outcalls, a powerful feature that allows ICP canisters to obtain data from external sources.

This application's logic is written in [Rust](https://internetcomputer.org/docs/building-apps/developer-tools/cdks/rust/intro-to-rust), a primary programming language for developing canisters on ICP.

## Features

- **Monthly Calendar View**: Interactive calendar for easy date navigation
- **Daily Notes**: Add and manage notes for each day
- **Historical Facts**: Get "On This Day" historical information via HTTPS outcalls
- **Task Management**: Mark notes as complete with visual indicators
- **Modern UI**: Beautiful, responsive design with ICP branding
- **On-chain Storage**: All data securely stored on the Internet Computer

## Project Structure

The `/backend` folder contains the Rust smart contract:

- `Cargo.toml`, which defines the crate that will form the backend
- `lib.rs`, which contains the actual smart contract, and exports its interface

The `/frontend` folder contains web assets for the application's user interface. The user interface is written using the React framework.

## Build and Deploy

To build and deploy this project locally, follow these steps:

### 1. Prerequisites

- Install the DFX SDK
- Have a local Internet Computer replica running

### 2. Build and Deploy

```bash
# Start the local replica
dfx start --background

# Deploy the canister
dfx deploy

# Start the frontend
npm start
```

### 3. Open the Application

Navigate to the URL provided by DFX to access your ICP Daily Planner.

## Development

For detailed build and deployment instructions, see the `BUILD.md` file.

## Technology Stack

- **Backend**: Rust with Internet Computer Protocol
- **Frontend**: React with modern CSS
- **Styling**: Custom CSS with ICP brand colors
- **Data Storage**: On-chain canister storage
- **External APIs**: HTTPS outcalls for historical data
