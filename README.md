# Uniport_MCP_Client

**Uniport_MCP_Client** is a Claude-compatible Model Context Protocol (MCP) extension that provides tools to query gene and protein information from UniProt. It allows clients like Claude to retrieve structured biological data through an MCP server interface.

---

## 🔬 Features

- ✅ Fetch **UniProt gene information** by gene symbol (e.g., `TP53`, `EGFR`)
- 🧬 Retrieve **tissue-specific protein expression**
- 📍 Access **subcellular localization** of proteins
- ⚙️ Works as a local **MCP server**
- ⚡ Supports **asynchronous** queries via FastAPI backend
- 📦 Pre-packaged as `.dxt` for use in Claude Extensions

---

## 🚀 Installation

Install the project locally in editable mode:

```bash
pip install -e .
```

---

## 🖥️ Running the MCP Server

Run the server (defined in `Profetch/mcp_server.py`) using:

```bash
python Profetch/mcp_server.py
```

You should see:

```
uniPROscope MCP server ready...
Available tools:
 - get_gene_info
 - get_subcellular_location
 - get_protein_expression
```

---

## 🧪 Using the Tools

This MCP extension exposes 3 functions:

- `get_gene_info(gene_symbol: str)`  
- `get_subcellular_location(gene_symbol: str)`  
- `get_protein_expression(gene_symbol: str)`  

Each can be called via JSON-RPC requests when loaded into a Claude environment.

---

## 📦 Packaging for Claude

Your Claude extension must follow this structure:

```
📁 Profetch.dxt
├── manifest.json         ← Must be at root
└── Profetch/             ← All source code here
    ├── mcp_server.py
    ├── bridge.py
    ├── __init__.py
```

To build your `.dxt`:

```python
import zipfile
import os

with zipfile.ZipFile("Profetch.dxt", "w", zipfile.ZIP_DEFLATED) as z:
    z.write("manifest.json")
    for root, _, files in os.walk("Profetch"):
        for file in files:
            path = os.path.join(root, file)
            z.write(path, os.path.relpath(path, ""))
```

---

## ⚙️ Development

- Python ≥ 3.8
- MCP Toolkit
- UniProt REST API
- Dependencies listed in `pyproject.toml` or `setup.py`

---

## 📄 License

MIT License — see `LICENSE` file for full terms.

---

## 👤 Author

**Shrihari Kamalan Kumaraguruparan**  
📧 kkshrihari@gmail.com  
🌐 [GitHub – Uniport_MCP_Client](https://github.com/ShrihariKamalanKumaraguruparan/Uniport_MCP_Client)
