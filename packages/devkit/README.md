# @stellarcommons/devkit CLI

`feeviz` CLI for analyzing Stellar transaction fees.

## Installation
```bash
npm install -g @stellarcommons/devkit
```

## Usage
```
feeviz [command]
```

## Commands

### `feeviz export`
Export fee stats from Horizon.

```bash
feeviz export --start 2024-01-01 --end 2024-01-31 --output fees.json
```

### `feeviz analyze`
Run analysis algorithms on fee data.

```bash
feeviz analyze --input fees.json --output analysis.json --algorithm percentile
```

### `feeviz visualize`
Generate charts from analysis results.

```bash
feeviz visualize --input analysis.json --output chart.png
```