# DEX POC - Decentralized Exchange

A Uniswap V2-based decentralized exchange proof of concept with plans for V3/V4 features.

## 🚀 Features

- **Token Swapping**: AMM with constant product formula (x × y = k)
- **Liquidity Provision**: Add/remove liquidity to earn 0.3% trading fees
- **Multiple Tokens**: Support for any ERC20 token pairs
- **Low Gas Costs**: Optimized V2 architecture
- **Future-Ready**: Architecture designed for V3/V4 migration

## 📁 Project Structure

```
DEX/
├── contracts/              # Foundry smart contracts
│   ├── src/
│   │   ├── core/          # Factory & Pair contracts
│   │   ├── periphery/     # Router contract
│   │   └── tokens/        # Mock ERC20 tokens
│   ├── script/            # Deployment scripts
│   ├── test/              # Contract tests
│   └── foundry.toml       # Foundry configuration
├── frontend/              # React frontend (planned)
├── docs/                  # Technical documentation
│   ├── architecture-comparison.md
│   ├── fee-structure.md
│   ├── amm-mathematics.md
│   └── liquidity-mechanics.md
└── README.md
```

## 🛠 Tech Stack

- **Smart Contracts**: Solidity 0.8.20 + Foundry
- **Network**: Arbitrum Sepolia (testnet)
- **Frontend**: React + TypeScript + Vite (planned)
- **Web3**: ethers.js + wagmi (planned)

## ⚡ Quick Start

### Prerequisites

- [Foundry](https://book.getfoundry.sh/getting-started/installation)
- [Git](https://git-scm.com/)
- [Node.js](https://nodejs.org/) (for frontend)

### 1. Clone & Setup

```bash
git clone https://github.com/amrrobb/dex-poc.git
cd dex-poc
```

### 2. Smart Contracts

```bash
cd contracts
forge install
forge build
forge test
```

### 3. Deploy to Arbitrum Sepolia

```bash
# Set environment variables
export PRIVATE_KEY=your_private_key
export ARBITRUM_SEPOLIA_RPC_URL=your_rpc_url
export ARBISCAN_API_KEY=your_api_key

# Deploy contracts
forge script script/Deploy.s.sol --rpc-url arbitrum_sepolia --broadcast --verify
```

### 4. Frontend (Coming Soon)

```bash
cd frontend
npm install
npm run dev
```

## 📊 Architecture Overview

### V2 AMM (Current Implementation)

- **Constant Product Formula**: x × y = k
- **Single Fee Tier**: 0.3% for all trading pairs
- **Full Range Liquidity**: Liquidity spread across all price ranges
- **Fungible LP Tokens**: ERC20 tokens representing pool shares

### Key Contracts

| Contract | Description |
|----------|-------------|
| `DexFactory` | Creates and manages trading pairs |
| `DexPair` | Core AMM logic with swap/mint/burn functions |
| `DexRouter` | User-facing interface for swaps and liquidity |
| `MockERC20` | Test tokens for development |

## 🔬 Testing

```bash
cd contracts
forge test -vv
```

## 📈 Future Roadmap

### Phase 1: V2 Foundation ✅
- [x] Constant product AMM
- [x] Single 0.3% fee structure
- [x] Basic swap functionality
- [x] Liquidity provision/removal

### Phase 2: Enhanced V2
- [ ] Multiple fee tiers (0.05%, 0.3%, 1%)
- [ ] Protocol fee implementation
- [ ] Advanced routing
- [ ] Gas optimizations

### Phase 3: V3 Concentrated Liquidity
- [ ] Tick-based price ranges
- [ ] NFT positions
- [ ] Capital efficiency improvements
- [ ] Active liquidity management

### Phase 4: V4 Hooks System
- [ ] Custom pool logic
- [ ] Dynamic fees
- [ ] Advanced DeFi integrations
- [ ] Governance features

## 📚 Documentation

- [Architecture Comparison](./docs/architecture-comparison.md) - V2 vs V3/V4 analysis
- [Fee Structure](./docs/fee-structure.md) - Detailed fee mechanism
- [AMM Mathematics](./docs/amm-mathematics.md) - Mathematical foundations
- [Liquidity Mechanics](./docs/liquidity-mechanics.md) - How liquidity works

## 🔧 Configuration

### Foundry Configuration

See `contracts/foundry.toml` for:
- Solidity compiler version
- Optimizer settings
- RPC endpoints
- Etherscan API keys

### Environment Variables

```bash
# Required for deployment
PRIVATE_KEY=your_wallet_private_key
ARBITRUM_SEPOLIA_RPC_URL=https://sepolia-rollup.arbitrum.io/rpc
ARBISCAN_API_KEY=your_arbiscan_api_key
```

## 🚨 Security

- ✅ Reentrancy protection
- ✅ Integer overflow checks
- ✅ Access control
- ✅ Input validation
- ⚠️ **Testnet only** - Not audited for mainnet

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests
5. Submit a pull request

## 📄 License

MIT License - see LICENSE file for details

## 🔗 Links

- [Uniswap V2 Docs](https://docs.uniswap.org/protocol/V2/introduction)
- [Foundry Book](https://book.getfoundry.sh/)
- [Arbitrum Docs](https://docs.arbitrum.io/)

---

**Note**: This is a proof of concept for educational purposes. Use at your own risk.