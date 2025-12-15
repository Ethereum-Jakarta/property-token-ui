# IndonesiaPropertyToken - RWA Real Estate Tokenization Platform

A decentralized application (dApp) for tokenizing real estate assets in Indonesia, built on Mantle Sepolia Testnet. This platform enables fractional ownership of property through ERC-20 compliant security tokens with built-in KYC compliance.

## Features

- **Property Tokenization**: View tokenized property details including location, valuation, and legal documents
- **KYC Compliance**: Integrated KYC verification system with multiple levels (Basic, Verified, Accredited)
- **Token Transfers**: Transfer tokens between verified investors with real-time balance updates
- **Portfolio Management**: Track your token holdings and ownership percentage
- **Admin Dashboard**: Manage KYC registrations, freeze accounts, and perform force transfers
- **Multi-wallet Support**: Connect via MetaMask, Rainbow, Coinbase Wallet, and more

## Tech Stack

- **Frontend**: React 19, TypeScript, Vite 6
- **Styling**: Tailwind CSS 4
- **Web3**: Wagmi 2, Viem 2, RainbowKit 2
- **State Management**: TanStack React Query 5
- **Routing**: React Router DOM 7
- **Notifications**: React Hot Toast
- **Icons**: Lucide React

## Smart Contracts

Deployed on **Mantle Sepolia Testnet** (Chain ID: 5003)

| Contract | Address |
|----------|---------|
| KYCRegistry | `0xF84796da575F3aCB1b563951fF0C22CB039d607B` |
| IndonesiaPropertyToken | `0x9D4eA7e7Eb182C628bb202a1521AA053868Cbeb6` |

### KYCRegistry Functions
- `registerInvestor`: Register new investor with KYC level
- `updateInvestor`: Update investor's KYC level
- `revokeInvestor`: Revoke investor's verification
- `isVerified`: Check if address is verified
- `getInvestorInfo`: Get detailed investor information

### IndonesiaPropertyToken Functions
- `transfer`: Transfer tokens between verified investors
- `balanceOf`: Get token balance of an address
- `canTransfer`: Check if transfer is allowed
- `freezeAccount`: Freeze an account (admin only)
- `unfreezeAccount`: Unfreeze an account (admin only)
- `forceTransfer`: Force transfer tokens (admin only)

## Getting Started

### Prerequisites

- Node.js 18+
- npm or yarn
- MetaMask or compatible Web3 wallet

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd property-token-ui

# Install dependencies
npm install

# Start development server
npm run dev
```

### Environment Setup

The app is pre-configured to connect to Mantle Sepolia Testnet. Make sure your wallet is configured with:

- **Network Name**: Mantle Sepolia Testnet
- **RPC URL**: https://rpc.sepolia.mantle.xyz
- **Chain ID**: 5003
- **Currency Symbol**: MNT
- **Block Explorer**: https://sepolia.mantlescan.xyz

### Get Test MNT

Visit the [Mantle Sepolia Faucet](https://faucet.sepolia.mantle.xyz) to get test MNT tokens.

## Project Structure

```
src/
├── components/
│   ├── layout/          # Header, Footer, Layout
│   ├── property/        # PropertyCard, PropertyDetails, PropertyStats
│   ├── kyc/             # KYCBadge, KYCStatusCard, InvestorList
│   ├── transfer/        # TransferForm, TransferPreview, TransferHistory
│   ├── stats/           # StatsCard
│   └── ui/              # Button, Input, Card, Badge, Modal, Alert, Spinner
├── config/
│   ├── chains.ts        # Chain configuration
│   ├── contracts.ts     # Contract addresses and ABIs
│   └── wagmi.ts         # Wagmi/RainbowKit configuration
├── hooks/
│   ├── usePropertyToken.ts      # Read hooks for PropertyToken
│   ├── usePropertyTokenWrite.ts # Write hooks for PropertyToken
│   ├── useKYCRegistry.ts        # Read hooks for KYCRegistry
│   └── useKYCRegistryWrite.ts   # Write hooks for KYCRegistry
├── lib/
│   ├── format.ts        # Formatting utilities
│   └── utils.ts         # General utilities
├── pages/
│   ├── Home.tsx         # Landing page
│   ├── Property.tsx     # Property details
│   ├── Portfolio.tsx    # User portfolio
│   ├── Transfer.tsx     # Token transfer
│   ├── KYCStatus.tsx    # KYC verification status
│   └── Admin.tsx        # Admin dashboard
├── types/
│   └── index.ts         # TypeScript type definitions
├── App.tsx              # Main app with routing
└── main.tsx             # Entry point with providers
```

## Available Scripts

```bash
# Development
npm run dev          # Start dev server at http://localhost:5173

# Build
npm run build        # Build for production

# Preview
npm run preview      # Preview production build

# Lint
npm run lint         # Run ESLint
```

## Pages

| Page | Path | Description |
|------|------|-------------|
| Home | `/` | Platform overview and key statistics |
| Property | `/property` | Detailed property information |
| Portfolio | `/portfolio` | User's token holdings |
| Transfer | `/transfer` | Send tokens to other investors |
| KYC Status | `/kyc` | View KYC verification status |
| Admin | `/admin` | Admin functions (owner only) |

## KYC Levels

| Level | Value | Description |
|-------|-------|-------------|
| NONE | 0 | Not verified |
| BASIC | 1 | Basic verification completed |
| VERIFIED | 2 | Full verification completed |
| ACCREDITED | 3 | Accredited investor status |

## License

MIT License

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
