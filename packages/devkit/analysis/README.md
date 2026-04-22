# Analysis Module

Functions for analyzing Stellar transaction fees.

## Functions

### `percentile(data, percentile)`
Calculate the nearest-rank percentile of a list of fees.

### `spike_detection(data, threshold)`
Detect fee spikes exceeding `threshold`.

## Usage
```bash
import { percentile } from '@stellarcommons/devkit/analysis'

const fees = [100, 200, 300]
const p95 = percentile(fees, 95)
```