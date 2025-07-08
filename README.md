# Groww AI MCP Server

A Model Context Protocol (MCP) server that provides AI-powered tools and resources for integrating with Groww's financial services and data.

## What is MCP?

The Model Context Protocol (MCP) is an open standard that enables AI assistants like Claude to securely connect with external data sources and tools. This Groww AI MCP server extends Claude's capabilities with financial market data and trading functionalities.

## Prerequisites

- Claude Desktop application installed on your system
- Valid Groww API credentials (API_KEY and API_SECRET)
- Operating system: Windows, macOS, or Linux

## Installation & Setup

### Step 1: Download the MCP Server

Download the appropriate executable file for your operating system:

- **Windows**: Download `win.exe` from [here](https://github.com/souvik131/groww-ai/raw/refs/heads/main/win.exe)
- **macOS**: Download `mac` from [here](https://github.com/souvik131/groww-ai/raw/refs/heads/main/mac)
- **Linux**: Download `linux` from [here](https://github.com/souvik131/groww-ai/raw/refs/heads/main/linux)

Save the downloaded file directly to your Downloads folder.

### Step 2: Get Your Groww API Credentials

1. Log in to your Groww account
2. Navigate to the API section in your account settings
3. Generate your API_KEY and API_SECRET
4. Keep these credentials secure and never share them publicly

### Step 3: Configure Claude Desktop

#### For Windows Users:

1. Locate your Claude Desktop configuration file at:

   ```
   %APPDATA%\Claude\claude_desktop_config.json
   ```

2. Open the file in a text editor and add the MCP server configuration:

```json
{
  "mcpServers": {
    "groww-server": {
      "command": "C:\\Users\\yourusername\\Downloads\\win.exe",
      "args": [],
      "env": {
        "API_KEY": "your_actual_api_key_here",
        "API_SECRET": "your_actual_api_secret_here"
      }
    }
  }
}
```

**Note**: Replace `yourusername` with your actual Windows username.

#### For macOS Users:

1. Locate your Claude Desktop configuration file at:

   ```
   ~/Library/Application Support/Claude/claude_desktop_config.json
   ```

2. Open the file in a text editor and add the MCP server configuration:

```json
{
  "mcpServers": {
    "groww-server": {
      "command": "/Users/yourusername/Downloads/mac",
      "args": [],
      "env": {
        "API_KEY": "your_actual_api_key_here",
        "API_SECRET": "your_actual_api_secret_here"
      }
    }
  }
}
```

**Note**: Replace `yourusername` with your actual macOS username.

#### For Linux Users:

1. Locate your Claude Desktop configuration file at:

   ```
   ~/.config/Claude/claude_desktop_config.json
   ```

2. Open the file in a text editor and add the MCP server configuration:

```json
{
  "mcpServers": {
    "groww-server": {
      "command": "/home/yourusername/Downloads/linux",
      "args": [],
      "env": {
        "API_KEY": "your_actual_api_key_here",
        "API_SECRET": "your_actual_api_secret_here"
      }
    }
  }
}
```

**Note**: Replace `yourusername` with your actual Linux username.

### Step 4: Make the Executable File Executable (macOS/Linux only)

For macOS and Linux users, you need to make the executable file executable:

```bash
# For macOS (replace yourusername with your actual username)
chmod +x /Users/yourusername/Downloads/mac

# For Linux (replace yourusername with your actual username)
chmod +x /home/yourusername/Downloads/linux
```

### Step 5: Restart Claude Desktop

After saving the configuration file, completely quit and restart the Claude Desktop application for the changes to take effect.

## Configuration Details

### Required Environment Variables

- `API_KEY`: Your Groww API key for authentication
- `API_SECRET`: Your Groww API secret for secure access

### Configuration Parameters

- `command`: Full path to the platform-specific executable
- `args`: Additional command-line arguments (empty array for default setup)
- `env`: Environment variables containing your API credentials

## Verification

To verify that the MCP server is working correctly:

1. Open Claude Desktop
2. Start a new conversation
3. Ask Claude about Groww-related queries or financial data
4. The MCP server should now provide enhanced responses with real-time financial information

## Troubleshooting

### Common Issues

1. **MCP Server Not Loading**

   - Verify the executable path is correct
   - Ensure the executable has proper permissions (macOS/Linux)
   - Check that your API credentials are valid

2. **Permission Denied Errors**

   - Run `chmod +x` on the executable file (macOS/Linux)
   - Ensure Claude Desktop has necessary permissions

3. **API Authentication Errors**

   - Verify your API_KEY and API_SECRET are correct
   - Check if your Groww API access is active
   - Ensure there are no extra spaces in your credentials

4. **Configuration File Not Found**
   - Create the directory structure if it doesn't exist
   - Ensure you're editing the correct configuration file for your OS

### Debug Steps

1. Check Claude Desktop logs for error messages
2. Verify the executable runs independently from command line
3. Test API credentials with a simple API call
4. Ensure the JSON configuration is valid (no syntax errors)

## Security Considerations

- Never commit your API credentials to version control
- Store your `claude_desktop_config.json` securely
- Regularly rotate your API keys
- Use environment variables for sensitive data when possible

## Support

If you encounter issues:

1. Check the troubleshooting section above
2. Verify your Groww API credentials are active
3. Ensure you're using the correct executable for your platform
4. Create an issue in this repository with detailed error information

## Contributing

Contributions are welcome! Please feel free to submit pull requests or create issues for bugs and feature requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Disclaimer

This MCP server is not officially affiliated with Groww. Use at your own risk and ensure compliance with Groww's API terms of service.
