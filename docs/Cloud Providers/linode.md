---
slug: /cloud-providers/linode
title: Linode
sidebar_label: Linode
---

# Linode

## Local Komiser CLI (Single account)

Komiser now supports multiple cloud accounts by default. Account configuration is done through the `config.toml` file, just pass in your account `API Token`.

We've also added 2 methods of persisting your account data.
### Postgres
#### Add to config.toml file
```
[postgres]
uri="postgres://postgres:komiser@localhost:5432/komiser?sslmode=disable"
```
### SQLite

```
[sqlite]
  file = "komiser.db"
```

### Configuring Credentials

Firstly grab your Personal Access token from your Linode account.

- Log in to the Cloud Manager
- Click on your username at the top of the screen and select `API Tokens` under the `My Profile` section.

Need help finding it? Head on over to the official Civo [documentation](https://www.linode.com/docs/products/tools/api/guides/manage-api-tokens/).

### Add your Linode API token to your confuriation file

```
[[linode]]
name="Staging-Account"
token="YOUR TOKEN"

[sqlite]
file="komiser.db
```
                                        

### Run it!
* That should be it. Try out the following from your command prompt to start the server:

```
komiser start 
```

* Point your browser to `http://localhost:3000`

## Local Komiser CLI (Multiple accounts)
Simply add more authentication blocks to the configuration file

```
[[linode]]
name="Development-Account"
token="YOUR DEV ACOUNT TOKEN"

[[linode]]
name="Staging-Account"
token="YOUR STAGING ACCOUNT TOKEN"

[[linode]]
name="Production-Account"
token="YOUR PROD ACCOUNT TOKEN"

[sqlite]
file="komiser.db
```
