# 🔍 `/review` - Comprehensive Code Review

This command performs thorough code analysis to ensure quality and maintainability.

```bash
/review
```

**What This Command Does:**

1. **Pre-analysis Setup**: Analyzes staged changes with `git diff --cached`
2. **Bug Detection**: Scans code for potential bugs, logic errors, and edge cases
3. **Performance Analysis**: Identifies performance bottlenecks and inefficient patterns
4. **Security Audit**: Checks for common security vulnerabilities (SQL injection, XSS, etc.)
5. **Code Style Review**: Ensures consistency with project standards and best practices
6. **Architecture Assessment**: Reviews code structure and design patterns

**Review Categories:**

- 🐛 **Critical Issues**: Bugs that could cause runtime errors
- ⚠️ **Warnings**: Potential issues that need attention
- 💡 **Suggestions**: Improvements for better code quality
- 🏗️ **Architecture**: Structural improvements and design patterns
- 🔒 **Security**: Security vulnerabilities and fixes

---
