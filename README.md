# 🌤️ Weather MCP Server — Powered by FastMCP

A simple **Model Context Protocol (MCP)** server built with [`FastMCP`](https://pypi.org/project/mcp/) that demonstrates how to expose custom tools to an AI runtime.  
This example defines a single tool, `get_weather`, which returns mock weather data for a given location.

---

## 🚀 Features

- ✅ Minimal, easy-to-understand MCP server
- ⚙️ Implements a `get_weather` tool
- 🧩 Ready to integrate with MCP-compatible clients
- 🐍 Written in clean, modern Python

---

## 🧠 How It Works

The `FastMCP` class wraps boilerplate setup and communication for MCP stdio servers.  
When the server starts, it exposes the `get_weather` function as a callable MCP tool that other agents or IDEs can invoke.

---

## 🧩 Code Overview

```python
from mcp.server.fastmcp import FastMCP

mcp = FastMCP("weather")

@mcp.tool()
def get_weather(location: str) -> str:
    """Get the current weather for a given location."""
    return f"The current weather in {location} is sunny with a temperature of 25°C."

if __name__ == "__main__":
    mcp.run()
⚡️ Getting Started
1️⃣ Clone the repo
bash
Copy code
git clone https://github.com/<your-username>/weather-mcp.git
cd weather-mcp
2️⃣ Create a virtual environment
bash
Copy code
uv venv
source .venv/bin/activate  # macOS/Linux
3️⃣ Install dependencies
bash
Copy code
uv pip install 'mcp[cli]'
4️⃣ Run the server
bash
Copy code
uv run python main.py
If everything is configured correctly, the server will start and listen for MCP stdio connections.

🔍 Example Usage
You can connect this MCP server to any MCP-compatible client (e.g., an IDE, LLM runtime, or agent).
When prompted, provide:

Setting	Value
Command	uv
Arguments	run --directory /path/to/weather-mcp python main.py

🧰 Project Structure
bash
Copy code
weather-mcp/
│
├── main.py          # MCP server source
├── pyproject.toml   # Project metadata (for uv/pdm)
└── README.md        # You are here
💡 Future Improvements
Integrate with a real weather API (e.g., OpenWeatherMap)

Add error handling and temperature units

Extend to multi-location forecasting and alerts

👨‍💻 Author
Bhavesh Kalluru
AI Engineer | Generative AI | LLM Applications | MCP Integrations
📍 Looking for full-time opportunities in the U.S.
