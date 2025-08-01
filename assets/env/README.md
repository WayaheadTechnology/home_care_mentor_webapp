# Environment Configuration Files

This folder contains environment-specific configuration files for the Ultimate Care Provider app.

## Files

- `env.dev` - Development environment configuration
- `env.qa` - QA/Staging environment configuration
- `env.prod` - Production environment configuration

## Usage

The app automatically loads the appropriate environment file based on the build mode:
- **Debug builds** → `env.dev`
- **Release builds** → `env.prod`

## File Format

Each file uses a simple key-value format:
```
KEY=value
```

Example:
```
DEBUG_MODE=true
API_TIMEOUT=30
DEV_API_URL=https://dev-api.ultimatecare.com
```

## Security Notes

- **Never commit sensitive data** (API keys, passwords) to version control
- **Production files** should be kept secure and not shared publicly
- **Use environment variables** for production deployments
- **Rotate credentials** regularly

## Adding New Environments

1. Create a new file following the naming convention: `env.{environment}`
2. Copy the structure from an existing file
3. Update the values for your specific environment
4. Update the app's environment detection logic if needed

## Troubleshooting

If the app can't find environment files:
1. Check that files are in the correct location (`env/` folder)
2. Verify file naming convention (`env.{environment}`)
3. Ensure files have proper read permissions
4. Check the console for error messages

For more detailed information, see the main [ENVIRONMENT_SETUP.md](../ENVIRONMENT_SETUP.md) file. 