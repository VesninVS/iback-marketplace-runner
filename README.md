# iBACK Marketplace Runner

Public GitHub Actions runner for the private iBACK marketplace monitor.

This repository contains **no marketplace data, no API keys and no unit economics**.

The scheduled workflow:
1. checks out the private `VesninVS/iback-marketplace-monitor` repository using a fine-grained token;
2. runs the read-only Ozon/Wildberries collector stored in that private repository;
3. writes `data/latest.json` and `data/history.jsonl` back to the private repository.

The marketplace credentials and the private-repository token are stored only in GitHub Actions Secrets.

Schedule: approximately 07:40 and 19:40 Asia/Tomsk.

Required Actions secrets:
- `OZON_CLIENT_ID`
- `OZON_API_KEY`
- `OZON_PERF_CLIENT_ID`
- `OZON_PERF_CLIENT_SECRET`
- `WB_API_TOKEN`
- `MONITOR_REPO_TOKEN`
