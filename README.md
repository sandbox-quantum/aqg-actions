# SandboxAQ GitHub Actions

A set of [GitHub Actions](https://github.com/features/actions) for using [SandboxAQ AQtive Guard](https://www.aqtiveguard.com/) to scan your your GitHub projects. 

## Supported Actions
- [AI SPM Inventory](aispm-inventory-action): Finds AI assets (models, agents, MCP servers, ...) in your code and adds them to your AQtive Guard inventory

Here's an example of using one of the Actions, in this case to test a Node.js project:

```yaml
name: Example workflow for Python using SandboxAQ AQtive Guard AI SPM
on: push
jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@master
      - name: Run AI SPM Inventory
        uses: sandbox-quantum/actions/aispm-inventory-action@master
        with:
          aqg_instance: https://some_url
        env:
          AQG_TOKEN: ${{ secrets.AQG_TOKEN }}
```

