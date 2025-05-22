# MCP Research Server

A demonstration project showcasing how to create a custom MCP (Model Control Protocol) server using the FastMCP framework. This implementation serves as a practical example of building an MCP server that integrates with arXiv to search, retrieve, and manage academic papers, providing a structured interface for AI-assisted research. The project leverages FastMCP's capabilities to create custom tools, resources, and prompts, making it an excellent reference for developing your own MCP servers.

## 🚀 Features

- **Paper Search**: Search for academic papers on arXiv by topic
- **Persistent Storage**: Automatically saves paper metadata for future reference
- **Topic Organization**: Organizes papers by research topics
- **RESTful API**: Exposes endpoints through FastMCP for easy integration
- **AI Integration**: Includes prompts for Claude AI to analyze research papers

## 🛠️ Prerequisites

- Python 3.11.11 (recommended)
- pip (Python package manager)
- Virtual environment (recommended)

> **Note**: This project is developed and tested with Python 3.11.11. While it may work with other Python 3.7+ versions, using 3.11.11 is recommended for compatibility.

## 🚀 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/teddytesfa/research-mcp-server.git
   cd mcp_project
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## 🏃‍♂️ Getting Started

1. Start the MCP server:
   ```bash
   python research_server.py
   ```

2. The server will start on `http://localhost:8001` by default.

## 🛠️ API Endpoints

### Tools
- `search_papers(topic: str, max_results: int = 5)`
  - Search for papers on arXiv
  - Returns: List of paper IDs

- `extract_info(paper_id: str)`
  - Get detailed information about a specific paper
  - Returns: Paper metadata as JSON

### Resources
- `papers://folders`
  - List all available topic folders

- `papers://{topic}`
  - Get papers for a specific topic

## 🤖 AI Integration

The server includes a prompt template for Claude AI to analyze research papers. Use the `generate_search_prompt` function to get started with AI-assisted research.

## 📁 Project Structure

```
mcp_project/
├── papers/                  # Directory for storing paper metadata
│   └── {topic}/             # Topic-specific directories
│       └── papers_info.json  # Paper metadata
├── research_server.py        # Main server implementation
└── README.md                # This file
```

## 📝 Example Usage

1. Search for papers on a topic:
   ```python
   # Example search for papers about "machine learning"
   paper_ids = search_papers("machine learning", max_results=3)
   ```

2. Get information about a specific paper:
   ```python
   paper_info = extract_info("2103.00001")
   print(paper_info)
   ```

## 📚 Learning Resources

This project is an implementation to demonstrate how to create your own MCP (Model Control Protocol) server. It showcases:

- Creating custom tools with `@mcp.tool()`
- Defining resources with `@mcp.resource()`
- Generating AI prompts with `@mcp.prompt()`
- Managing server state and persistence
- Integrating with external APIs (arXiv)

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

