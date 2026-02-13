# PoliFlow

PoliFlow provides a workflow-aware approach to enforce control-flow policies in serverless applications by extracting allowed execution paths from workflow descriptors and enforcing them at runtime on Knative Services. This repository aggregates and links to the open-source components: [Extractor](https://doi.org/10.5281/zenodo.18625795), [Enforcer](https://doi.org/10.5281/zenodo.18625781), [Language](https://doi.org/10.5281/zenodo.18625802), [Test Applications](https://doi.org/10.5281/zenodo.18625740), and [Evaluation assets](https://doi.org/10.5281/zenodo.18625790).​

## Extractor

The repository contains two Extractor versions:
- CNCF Serverless Workflow: Parses v0.8 descriptors (and optional subflows) to produce allowed-paths in JSON (for enforcement) and YAML (human-readable); examples and pre-extracted outputs are included.
- PoliFlow Language: For direct-call applications (function-to-function/services), outputing inbound and outbound rules; requires installing the PoliFlow language package locally before running.

The repository is accessible using the URL [https://doi.org/10.5281/zenodo.18625795](https://doi.org/10.5281/zenodo.18625795)

## Enforcer

The implemented Enforcer works as an extension to Knative's `queue-proxy` that enforces Extractor-produced allowed paths (for the CNCF Serverless Workflow v0.8) on each protected Knative Service.

The repository is accessible using the URL [https://doi.org/10.5281/zenodo.18625781](https://doi.org/10.5281/zenodo.18625781)

## Language

The PoliFlow Declarative Language is used for defining control-flow policies in serverless direct-call applications. Moreover, this repository holds a Python package used by the PoliFlow Language Extractor.

The repository is accessible using the URL [https://doi.org/10.5281/zenodo.18625802](https://doi.org/10.5281/zenodo.18625802)

## Test Applications

This repository implements minimal applications used to validate enforcement across workflow patterns (loop, parallel, operation, conditional) with Knative Services and SonataFlow-based workflows. Each application includes allowed-path annotations extracted from the workflow and can be modified to verify that the Enforcer blocks unintended flows.

The repository is accessible using the URL [https://doi.org/10.5281/zenodo.18625740](https://doi.org/10.5281/zenodo.18625740)

## Evaluation

The Evaluation repository holds the scripts for deployment/teardown timing and latency measurements across several scenarios (Refund, Valve, long-sequence, long-parallel) used in the PoliFlow article "PoliFlow: Inferring Control-Flow Policies from Serverless Workflows".

The repository is accessible using the URL [https://doi.org/10.5281/zenodo.18625790](https://doi.org/10.5281/zenodo.18625790)
​
