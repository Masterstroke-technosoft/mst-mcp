# MST-MCP Server

An official Model Context Protocol (MCP) server for the **MST Chain** ecosystem. This server provides tools for LLMs (like Claude) to search, list, and retrieve MST developer documentation (APIs, wallets, transactions, authentication, etc.).

## 🚀 Deployed Endpoint
* **Base URL (SSE Transport):** `http://<YOUR_AWS_EC2_IP_OR_DOMAIN>:<PORT>/sse`
* **Favicon / Branding:** `http://<YOUR_AWS_EC2_IP_OR_DOMAIN>:<PORT>/favicon.png`

---

## 🛠 Exposed Tools

All tools are read-only lookup tools with custom annotations:

1. **`list_documents`**
   * **Description:** Lists all available developer documentation files in the server.
   * **Annotations:** `readOnlyHint: true`, `title: "List Documents"`

2. **`read_document`**
   * **Description:** Reads and returns the contents of a specific documentation file (e.g., `SDK.txt`).
   * **Annotations:** `readOnlyHint: true`, `title: "Read Document"`

3. **`search_documents`**
   * **Description:** Searches for a keyword or query across all files and returns matching lines with line numbers.
   * **Annotations:** `readOnlyHint: true`, `title: "Search Documents"`

---

## 💡 Example Prompts to Try in Claude

After connecting this server as a connector, you can ask Claude:

* **Example 1 (Listing docs):** 
  > "Check my mcp is in working and list all documentation files."
* **Example 2 (Searching keywords):** 
  > "Search the developer docs for wallet integration details."
* **Example 3 (Retrieving document content):** 
  > "Read the documentation on transaction structure."

---

## 🏗 Setup & Deployment

### Local Development
To run the server locally:
1. Initialize virtual environment and install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
2. Start the server:
   ```bash
   python server.py
   ```

### Deploying on AWS EC2
We have provided a dedicated deployment guide for AWS EC2. 
Please refer to the [`DEPLOYMENT.md`](./DEPLOYMENT.md) file for comprehensive, step-by-step instructions on setting up your EC2 instance natively or via Docker.
