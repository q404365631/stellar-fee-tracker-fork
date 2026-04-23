# @stellarcommons/devkit CLI

`feeviz` CLI for analyzing Stellar transaction fees.

## Installation

### Via npm (recommended)
```bash
npm install -g @stellarcommons/devkit
```

### Via GitHub
```bash
git clone https://github.com/StellarCommons/stellar-fee-tracker.git
cd stellar-fee-tracker/packages/devkit
npm install -g .
```

## Usage

### Basic command structure
```bash
feeviz [command] [options]
```

### Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `HORIZON_URL` | Custom Horizon API endpoint | `https://horizon.stellar.org` |
| `NETWORK` | Network type (`mainnet` or `testnet`) | `mainnet` |
| `OUTPUT_DIR` | Default output directory for exports | `./output` |

### Commands

#### `feeviz export`
Export fee stats from Horizon.

```bash
# Export with default settings
feeviz export

# Export specific date range
feeviz export --start 2024-01-01 --end 2024-01-31 --output fees.json

# Export testnet data
NETWORK=testnet feeviz export --output testnet-fees.json
```

#### `feeviz analyze`
Run analysis algorithms on fee data.

```bash
# Analyze with percentile algorithm
feeviz analyze --input fees.json --output analysis.json --algorithm percentile

# Analyze with custom Horizon endpoint
HORIZON_URL=https://custom-horizon.example.com feeviz analyze --input fees.json
```

#### `feeviz visualize` (or `feeviz visu`)
Generate visualizations from analysis data.

```bash
feeviz visualize --input analysis.json --output chart.png --type line
```

## Development

```bash
# Clone and setup
git clone https://github.com/StellarCommons/stellar-fee-tracker.git
cd stellar-fee-tracker/packages/devkit
npm install

# Run tests
npm test

# Build
npm run build
```

## Configuration File

You can also create a `.feevizrc.json` in your project root:

```json
{
  "horizonUrl": "https://horizon.stellar.org",
  "network": "mainnet",
  "outputDir": "./output"
}
```
