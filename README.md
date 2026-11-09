# EVM DEX Bot (BSC / PancakeSwap Edition)

Automated trading bot for EVM-compatible DEXes, currently configured and tested for **Binance Smart Chain (BSC)** and **PancakeSwap V2**.

Originally based on the 2022 AlphaBot for KCC. This version has been adapted to run on modern Python and switched to BSC.

## Features

- Direct on-chain trading via web3.py (no MetaMask required)
- Limit orders, stop-loss, and trailing stops
- Multi-token monitoring
- Private key encryption with password
- Liquidity and basic safety checks
- Runs fully locally on your machine

## Current Configuration

- **Chain**: Binance Smart Chain (BSC)
- **DEX**: PancakeSwap V2
- **Base token**: WBNB
- **Python**: 3.11 recommended

## Important Warnings

- This is a modified 2022 codebase. It does **not** have modern MEV / sandwich protection.
- Only use money you can afford to lose completely.
- Use a dedicated wallet with limited funds.
- Private keys are encrypted when `ENCRYPTPRIVATEKEYS` is set to `true`.

## Installation

### 1. Prerequisites
- Python 3.11 (recommended)
- Git

### 2. Clone the repo
```bash
git clone https://github.com/maxzysparks/EVM.git
cd EVM
```

### 3. Create a virtual environment
```bash
py -3.11 -m venv venv
source venv/Scripts/activate   # Windows (Git Bash)
# or
venv\Scripts\activate          # Windows (CMD/PowerShell)
```

### 4. Install dependencies
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

> Note: Some packages may require `--only-binary=:all:` or specific version pinning on Python 3.11.

## Configuration

1. Edit `settings.json`:
   - Set your BSC wallet address (checksum format)
   - Set `"EXCHANGE": "pancakeswap"`
   - Set `"EXCHANGEVERSION": "2"`
   - Set `"USECUSTOMNODE": "true"` and a reliable BSC RPC
   - Set `"ENCRYPTPRIVATEKEYS": "true"` (recommended)

2. Edit `tokens.json` with the pairs you want to trade (start with liquid pairs like CAKE/WBNB and very small amounts).

## Running the Bot

```bash
python AlphaBot.py
```

- On first run with encryption enabled, it will ask you to create a password and enter your private key.
- Make sure your wallet has enough BNB for gas + the trade amount.

## Supported DEXes (original code)

The original bot supported many DEXes. This version has been verified on:
- PancakeSwap (BSC)

Other chains may work with configuration changes but are untested in this fork.

## License

See `LICENSE` file.

## Disclaimer

This software is provided as-is. Trading cryptocurrency involves substantial risk of loss. You are solely responsible for any funds used with this bot.
