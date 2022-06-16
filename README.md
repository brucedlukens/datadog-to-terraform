# Datadog to Terraform Converter

Converts Datadog monitor and dashboard JSON into Terraform HCL code.

## How to Use

### CLI

1. Clone the repo
2. Make sure you're on node 16
3. `yarn install`
4. `yarn build`
5. `convert <your-datadog-json-file>.json`
6. Output will be on the terminal, you will need to change the name of the dashboard from `replaceMeNow`.


### Limitations
There is currently a limitation with dashboard components made up of multiple queries. These need to be hand-adjusted but will be caught with `terraform plan`.
Currently these queries get repeated N times, with N being the number of queries making up the single query.
These queries also need to be wrapped with `query {}`
