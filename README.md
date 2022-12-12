# Minimal cluster with open source tools
This repository contains a minimal set of tools that can be deployed on a cluster to provide a basic set of services. The goal is to bootstrap a cluster to test its workings.

## Tools
1. cert-manager
2. imps
3. kubernetes-external-secrets
4. traefik

## Usage
Each tool is present in its own folder and is a Helm chart that depends on an upstream helm chart. These helm charts are configured to be deployed using the configuration present in the `values.yaml` file. Some of the deployments might require additional secrets to be deployed.

### cert-manager
This tool needs a DNS manager to connect to. We use Cloudflare and as such we deploy with a cloudflare API key.

### kubernetes-external-secrets
This tool needs a backend secret store to work. We use Azure Key Vault and the current secret resource is configured to use that service. It needs to be updated to reflect the service that is being used.