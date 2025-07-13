# 🔧 `/fix` - Automated Bug Fixing

Intelligent bug detection and automated fixing with strict type checking.

```bash
/fix
```

With specific focus:

```bash
/fix --mypy-only
/fix --ruff-only
```

**What This Command Does:**

1. **Error Log Analysis**: Analyzes stack traces and error messages
2. **Type Checking**: Runs rigorous mypy analysis from root folder
3. **Code Quality**: Performs strict ruff linting and formatting
4. **Pattern Recognition**: Identifies common error patterns and fixes
5. **Automated Fixes**: Implements fixes for common issues
6. **Regression Prevention**: Ensures fixes don't introduce new bugs

**Fix Categories:**

- 🐛 **Runtime Errors**: Fixes for crashes and exceptions
- 🔤 **Type Errors**: Resolves mypy type checking issues
- 📏 **Style Issues**: Fixes ruff linting violations
- 🔄 **Logic Errors**: Corrects flawed business logic
- 🚨 **Critical Fixes**: Immediate fixes for blocking issues

**Strict Quality Checks:**

- **MyPy**: Comprehensive type checking from project root
- **Ruff**: Aggressive linting with all rules enabled
- **Error Handling**: Proper exception handling patterns
- **Code Style**: Consistent formatting and structure
