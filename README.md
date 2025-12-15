# PoliFlow

PoliFlow provides a workflow-aware approach to enforce control-flow policies in serverless applications by extracting allowed execution paths from workflow descriptors and enforcing them at runtime on Knative Services. This repository aggregates and links to the open-source components: [Extractor](https://zenodo.org/records/17914092?preview=1&token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6IjhiMTQwN2QwLWY3ODItNDMyNy05NjBhLTE1YWIyYmM4MDUxNiIsImRhdGEiOnt9LCJyYW5kb20iOiI1M2EzY2VlNzFmN2I0Y2Q3MDNiNjBiOTFlMTM5YjJkOSJ9.A3Y-wwljKCCI6ayPK1OJyig2XJIdl2lnyaneabGD2uDKYVIU53ArtVKpZD1lDAOVZwcrGEhmUW4dHoS_QO0sQw), [Enforcer](https://zenodo.org/records/17915395?preview=1&token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6IjllMGYyNWVjLTRiNDctNDAyYy1iNmZlLTBkZTFlNTA2YWUwMiIsImRhdGEiOnt9LCJyYW5kb20iOiJlZTZiMGU1OTE3MzE4YTM5M2EzYjFkYTZjZWVmNmUyMyJ9.3XoNUwRNJTFN39KOhm1hm-hhHtoyDyQaChwWVfIFQftOXQ-OhST-qhu14ZSFcb-p00goq_K8ZtP1ONM-ZzXdiQ), [Language](https://zenodo.org/records/17913926?preview=1&token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6IjE2MGMxZWRhLTE5OTctNGQ5NS1iMDQ4LWIzNTdlNWMwZjA4MiIsImRhdGEiOnt9LCJyYW5kb20iOiJmNTgxMzIyMTA1ODQ1M2VhYWFjZmUxNjkwZDgzYzFkYiJ9.3qfRPwpg9x3h6bbJjvHODjwKLui3JQPF4YhIIbY549mdMXj2HDOSAgKx7ul9iyuozIE0rrglqH0IKfb5dP9p8w), [Test Applications](https://zenodo.org/records/17916336?preview=1&token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6IjRkZWRmMjcwLTYzZWUtNDBlZi1hOWJmLTYxYmVjN2Y2NzBkZCIsImRhdGEiOnt9LCJyYW5kb20iOiJlNThlZGFkNzRlZjY5OTQ5ZWM0NTgzNjcwZTExOTA0MiJ9.o2Ls14QKnMVw1yY_nbulgMdec-PYgbirAeqiKbIbKlNEahrA8M5qj3yKbkVGyoN6r9iP2qwPDhAuuitxCmGTBA), and [Evaluation assets](https://zenodo.org/records/17913703?preview=1&token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6IjYzNGFkYWZiLWU3N2UtNDkzYy1iNDQyLTQ2ZDQzMjljNGRhZSIsImRhdGEiOnt9LCJyYW5kb20iOiIzNWQzNGEzNGExOTVlNDRkNGRmZmJiZDU1MjM5ODMxZCJ9.Kxx2KkGeL8oyeAWKSilg9z5jjt4KwCVvw5MhXPnz7QJWa0KwGwRMRzukT8P1olfbx33e77zc3bMSkMPkI6azzA).​

## Extractor

The repository contains two Extractor versions:
- CNCF Serverless Workflow: Parses v0.8 descriptors (and optional subflows) to produce allowed-paths in JSON (for enforcement) and YAML (human-readable); examples and pre-extracted outputs are included.
- PoliFlow Language: For direct-call applications (function-to-function/services), outputing inbound and outbound rules; requires installing the PoliFlow language package locally before running.

The repository is accessible using the URL https://tinyurl.com/poliflow-extractor

## Enforcer

The implemented Enforcer works as an extension to Knative's `queue-proxy` that enforces Extractor-produced allowed paths (for the CNCF Serverless Workflow v0.8) on each protected Knative Service.

The repository is accessible using the URL https://tinyurl.com/poliflow-enforcer

## Language

The PoliFlow Declarative Language is used for defining control-flow policies in serverless direct-call applications. Moreover, this repository holds a Python package used by the PoliFlow Language Extractor.

The repository is accessible using the URL https://tinyurl.com/poliflow-language

## Test Applications

This repository implements minimal applications used to validate enforcement across workflow patterns (loop, parallel, operation, conditional) with Knative Services and SonataFlow-based workflows. Each application includes allowed-path annotations extracted from the workflow and can be modified to verify that the Enforcer blocks unintended flows.

The repository is accessible using the URL https://tinyurl.com/poliflow-test-applications

## Evaluation

The Evaluation repository holds the scripts for deployment/teardown timing and latency measurements across several scenarios (Refund, Valve, long-sequence, long-parallel) used in the PoliFlow article "PoliFlow: Inferring Control-Flow Policies from Serverless Workflows".

The repository is accessible using the URL https://tinyurl.com/poliflow-evaluation
​
