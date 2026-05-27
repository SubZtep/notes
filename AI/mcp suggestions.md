Let me suggest the most useful MCP servers for writing Playwright tests together:

  Recommended MCP Servers for E2E Testing

  1. PostgreSQL MCP Server (Highest Priority)

  Allows direct database inspection/queries during test development:
  {
    "mcpServers": {
      "postgres": {
        "command": "npx",
        "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://testuser:testpass@localhost:5433/xploro_test"]
      }
    }
  }
  Why: I can verify test data, check what's seeded, debug why tests fail by inspecting DB state

  2. Fetch MCP Server (High Priority)

  Test API endpoints directly:
  {
    "fetch": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-fetch"]
    }
  }
  Why: Quickly test API responses, understand what data the portal receives, debug API issues

  3. Docker MCP Server (Medium Priority)

  Manage containers and check logs:
  {
    "docker": {
      "command": "docker-mcp",
      "args": []
    }
  }
  Why: Check container health, view logs when tests fail, restart services if needed

  4. Playwright Inspector/Debugger (Nice to Have)

  While there isn't an official Playwright MCP yet, we can work with what we have using bash commands

  My Recommendation

  Start with PostgreSQL + Fetch MCP servers. Here's what I can help with once they're set up:

  1. Inspect seeded data to understand what users/orgs exist
  2. Write new tests by querying available test data
  3. Debug test failures by checking DB state mid-test
  4. Verify API responses match what the portal expects
  5. Suggest test improvements based on actual data structure

  Should I create the .claude/mcp.json config with the PostgreSQL and Fetch servers to get started? Then we can run your setup commands and I'll be able to help write
   tests much more effectively!