---
name: python-development
description: Guide for Python development in this project. Use when writing Python scripts, especially for admin/database tasks. Emphasizes no error handling (fail fast), Windows terminal compatibility, and proper virtual environment usage.
---

# Writing Python

Guide for Python development in this project.

## Quick Reference

**Code organization:**
- Imports at top
- Main logic first, helpers towards bottom (read main logic first)
- Include usage note at top showing how to run from project root and how to run related tests if applicable

**Critical rules:**
- **NEVER use try/catch, fallbacks, or defaults** - Create visible failures with full stack traces
- **Replace Unicode with ASCII** - Avoid encoding issues on Windows terminals
- **No empty `__init__.py`** unless necessary

**Package Installation:**
- Always use PowerShell commands instead of VS Code extensions or MCP. 
- Always use venv.
- First add it to `requirements.txt`, then run `& .venv/Scripts/Activate.ps1; pip install -r requirements.txt` to do the install.

**Running Python:**
- Always activate .venv first and run from the project root: `& .venv/Scripts/Activate.ps1; path-to-file/python script.py`
- Create temporary test scripts instead of complex PowerShell commands (to avoid syntax errors which are very difficult to avoid), delete after use.

**Testing:**
- If file has test reference at top and you change it, run tests
- Always address warnings
- Add `pytest` tests as appropriate.
