# SandboxAQ Cybersecurity AI-SPM Inventory Scan

A [GitHub Action](https://github.com/features/actions) for using [SandboxAQ](https://www.sandboxaq.com/) AQtive Guard
AI-SPM functionality. This action scans your code using static analysis to detect AI assets (such as models, agents, MCP servers, ...).
Once the inventory is created, it'll be sent to your AQtive Guard instance, where it'll be enriched
with additional information and analyzed for issues. You can inspect the results in your AQtive Guard web interface.

You can use the Action as follows:

```yaml
name: Example workflow for Python using SandboxAQ Cybersecurity AI-SPM
on: push
jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - name: Run AI-SPM Inventory
        uses: sandbox-quantum/actions/aispm-inventory-action@master
        with:
          aqg_instance: https://some_url
        env:
          AQG_TOKEN: ${{ secrets.AQG_TOKEN }}
```

## Properties

This Action has properties which are passed to the underlying image, either as an explicit input variable (passed using `with`)
or as an environment variable (using `env`).

| Property     | Default | Description                                                                                         |
| ------------ | ------- | --------------------------------------------------------------------------------------------------- |
| aqg_instance |         | URL of your AQtive Guard instance (input variable)                                                  |
| AQG_TOKEN    |         | Authentication token to connect to AQtive Guard (environment variable)                              |

