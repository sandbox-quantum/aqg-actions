# SandboxAQ AQtive Guard GitHub Actions

A set of [GitHub Actions](https://github.com/features/actions) for using [SandboxAQ AQtive Guard](https://www.aqtiveguard.com/) to scan your your GitHub projects. 

## Supported Actions
- [AI-SPM Inventory](aispm-inventory-action): Finds AI assets (models, agents, MCP servers, ...) in your code and adds them to your AQtive Guard inventory

Here's an example of using one of these Actions, to scan a repository for AI assets:

```yaml
name: Example workflow using SandboxAQ AQtive Guard AI-SPM
on: push
jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@master
      - name: Run AI-SPM Inventory detection
        uses: sandbox-quantum/aqg-actions/aispm-inventory-action@master
        with:
          aqg_instance: https://some_url
          aqg_client_id: ${{ secrets.AQG_CLIENT_ID }}
          aqg_client_secret: ${{ secrets.AQG_CLIENT_SECRET }}
```

