# Uniport_MCP_Client

Uniport_MCP_Client is a Python package and Claude-compatible Model Context Protocol (MCP) extension that queries UniProt for detailed human gene and protein information. It offers asynchronous tools to fetch gene data, protein expression, and subcellular localization via the UniProt REST API.

## Features
- Retrieve gene information by official gene symbol (e.g., TP53, EGFR)
- Access tissue-specific protein expression summaries
- Fetch subcellular localization details
- Seamlessly integrates with Claude MCP clients
- Asynchronous and efficient data fetching

## Installation
Install the package in editable mode for development:
```bash
pip install -e .
Usage
Run the MCP server locally:

bash
Copy
python Profetch/mcp_server.py --serve
This exposes tools:

get_gene_info

get_protein_expression

get_subcellular_location

Use these tools via MCP clients or JSON-RPC calls with gene symbols as input.

Packaging for Claude
Ensure manifest.json at the root of the package with correct "entry": "Profetch/mcp_server.py"

Zip using zip.py or similar script to create Profetch.dxt with the manifest at root and .py files inside Profetch/.

Upload .dxt in Claude Extensions developer mode.

Development
Python 3.8+

Dependencies listed in pyproject.toml (requests package required)

Tests recommended with pytest

License
MIT License (see LICENSE file)

Author
Shrihari Kamalann Kumaraguruparan
Email: kkshrihari@gmail.com
GitHub: https://github.com/ShrihariKamalanKumaraguruparan/Uniport_MCP_Client
