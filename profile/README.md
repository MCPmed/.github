# MCPmed 
![Graphical Abstract](./graphical%20abstract.png)
More info: https://mcpmed.org
## Introduction
Welcome to MCPmed, a comprehensive collection of Model Context Protocol (MCP) servers designed for seamless integration with biological and biomedical databases. This project aims to bridge the gap between large language models and scientific data resources, enabling AI-assisted research workflows in bioinformatics and computational biology.

## Current Phase
* **Active Development**: Multiple MCP servers are operational, providing access to key databases including GEO, STRING, and EMBL-EBI resources
* **Standardization Efforts**: Establishing consistent patterns and interfaces across all MCP implementations
* **Community Growth**: Building a network of researchers and developers to expand database coverage and improve existing tools

## Core Capabilities
* **Direct Database Access**: LLMs can query and retrieve data from major biological databases without intermediate APIs
* **Standardized Interfaces**: Consistent MCP protocol implementation across all database connectors
* **Extensible Architecture**: Cookie-cutter templates enable rapid development of new database integrations
* **Scientific Focus**: Tailored specifically for bioinformatics and biomedical research applications

## Active MCP Servers

| Repository | Description | Language | License |
|------------|-------------|----------|---------|
| **paperscraperMCP** | Tools to scrape publications & metadata from PubMed, arXiv, medRxiv, bioRxiv, and chemRxiv. Forked from jannisborn/paperscraper. | Python | MIT |
| **GEOmcp** | MCP server for accessing Gene Expression Omnibus (GEO) data through NCBI E-Utils API. Enables programmatic access to gene expression datasets. | Python | BSD-3-Clause |
| **EMBL-EBI-Protein-mcp** | MCP server for accessing EMBL-EBI protein databases and services. | Python | BSD-3-Clause |
| **UCSCCBmcp** | MCP server for UCSC Cell Browser integration. | Python | BSD-3-Clause |
| **STRINGmcp** | MCP implementation for STRING DB - protein-protein interaction networks database. | Python | BSD-3-Clause |
| **PLSDBmcp** | MCP server linking to PLSDB (Plasmid Database) for accessing plasmid sequences and metadata. | Python | Not specified |

## Development Tools & Templates

| Repository | Description | Language | License |
|------------|-------------|----------|---------|
| **breadcrumbs** | Cookie cutter template for laying LLM traces through web services. Useful for debugging and monitoring LLM interactions. | HTML | BSD-3-Clause |
| **Cookiecutter-MCPmed** | Cookie cutter template for setting up medical/biomedical MCP project structures. | Python | BSD-3-Clause |
| **.github** | GitHub configuration and workflow files. | - | - |
## MCPmed Template

### Template for python mcp package
Find the template [here](https://github.com/MCPmed/Cookiecutter-MCPmed).
Ideally, you can use the template to create a new MCPmed package to wrap an existing API.
```bash
cookiecutter MCPmedtemplate
```

### Other templates coming soon

# Contributing

Contributions are welcome. Priority areas include:

- **New Database Connectors**: Implement MCP servers for additional biological databases
- **Performance Improvements**: Optimize existing implementations
- **Bug Fixes**: Address issues in current MCP servers
- **Documentation**: Improve technical documentation and usage examples

## Guidelines

- Use the Cookiecutter-MCPmed template for new MCP servers
- Follow PEP 8 for Python code
- Include unit tests for new functionality
- Maintain BSD-3-Clause or MIT licensing compatibility
- Submit pull requests with clear descriptions

For questions or discussions, use the repository Issues section.