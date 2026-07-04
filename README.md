# ONION

This repository contains the implementation of ONION for sparse knowledge graph reasoning.

## Setup

```bash
make setup
tar xvzf data-release.tgz
```

## Process Data

```bash
./experiment.sh configs/<dataset>.sh --process_data <gpu-ID>
```

## Train ONION

Train the ConvE embedding model first:

```bash
./experiment-emb.sh configs/<dataset>-conve.sh --train <gpu-ID>
```

Then train ONION:

```bash
./experiment-rs.sh configs/<dataset>-rs.sh --train <gpu-ID>
```

## Evaluate ONION

```bash
./experiment-rs.sh configs/<dataset>-rs.sh --inference <gpu-ID>
```

To save beam-search paths:

```bash
./experiment-rs.sh configs/<dataset>-rs.sh --inference <gpu-ID> --save_beam_search_paths
```

Available datasets and experiment settings can be found in the `configs` directory.
