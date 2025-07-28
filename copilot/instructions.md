# GitHub Copilot Instructions for Mnemoverse Project

## 🏗️ Multi-Repository Architecture Overview

This is the **ROOT** of the Mnemoverse multi-repository project. We have separate repositories for different concerns:

```
mnemoverse/  ← ROOT REPOSITORY (coordination & scripts)
├── mnemoverse-web-client/        ← Landing page (Vite + Vanilla JS)
├── mnemoverse-docs/              ← Documentation & MCP server (VitePress + TypeScript)
├── mnemoverse-research-library/  ← AI Research Library (Python + FastAPI)
├── mnemoverse-chat-ui/           ← Chat interface (Next.js + assistant-ui)
├── mnemoverse-arch/              ← Multi-agent orchestration (LangGraph + Mem0)
├── Unity-Prototype/              ← Unity 3D prototype (C#)
└── dev/                          ← Development planning and documentation
```

## 🚀 Current Project Status

### **Active Development (Public Ready):**
- **MCP Documentation Server** - Published on npm as `@mnemoverse/mcp-docs-server`
- **Research Library** - 300+ curated AI research sources with semantic search
- **Chat UI** - Next.js interface with LangGraph integration and tool support
- **Documentation** - Comprehensive guides, manifesto, and technical specifications

### **In Development:**
- **Mnemoverse Arch** - Multi-agent orchestration system (LangGraph + Mem0)
- **Universal MCP Index** - Tool coordination across development environments
- **Agent Memory Systems** - Persistent knowledge infrastructure

## 🚨 CRITICAL RULES - WORKSPACE AWARENESS

### 1. **Always Check Your Location**
Before any operation, determine which repository you're working in:
- **Root (`/mnemoverse/`)**: Multi-repo coordination, monorepo scripts
- **Web Client (`/mnemoverse-web-client/`)**: Vite, Node.js, package.json
- **Docs (`/mnemoverse-docs/`)**: VitePress, TypeScript MCP server, package.json  
- **Research Library (`/mnemoverse-research-library/`)**: Python, FastAPI, requirements.txt
- **Chat UI (`/mnemoverse-chat-ui/`)**: Next.js, assistant-ui, package.json
- **Mnemoverse Arch (`/mnemoverse-arch/`)**: Python, LangGraph, Mem0, requirements.txt
- **Unity (`/Unity-Prototype/`)**: C#, Unity project

### 2. **Respect Environment Boundaries**
- **NEVER** install Python packages in Node.js repositories
- **NEVER** run `npm install` in Python repositories  
- **NEVER** mix virtual environments between repositories
- **ALWAYS** use the correct package manager for each repo

### 3. **Virtual Environment Strategy**
```bash
# Python repositories (research-library, mnemoverse-arch)
cd mnemoverse-research-library/
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt

cd mnemoverse-arch/
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Node.js repositories (docs, web-client, chat-ui)
cd mnemoverse-docs/
npm install

cd mnemoverse-web-client/
npm install

cd mnemoverse-chat-ui/
npm install
```

## 📁 Repository-Specific Guidelines

### 🌐 Web Client (`mnemoverse-web-client/`)
- **Technology**: Vite + Vanilla JavaScript + Three.js
- **Package Manager**: npm
- **Commands**: `npm run dev`, `npm run build`
- **Environment**: Node.js
- **Purpose**: Simple landing page with particle animations

### 📚 Documentation (`mnemoverse-docs/`)
- **Technology**: VitePress + TypeScript MCP server
- **Package Manager**: npm  
- **Commands**: `npm run docs:dev`, `npm run docs:build`, `npm run mcp:dev`
- **Environment**: Node.js
- **Purpose**: Documentation, research library, and MCP server for AI assistants
- **Published**: `@mnemoverse/mcp-docs-server` on npm

### 🔬 Research Library (`mnemoverse-research-library/`)
- **Technology**: Python + FastAPI + Docker
- **Package Manager**: pip
- **Commands**: `python main.py`, `docker-compose up`
- **Environment**: Python virtual environment
- **Purpose**: AI-powered research library with 300+ curated sources

### 💬 Chat UI (`mnemoverse-chat-ui/`)
- **Technology**: Next.js + assistant-ui + LangGraph
- **Package Manager**: npm
- **Commands**: `npm run dev`, `npm run build`
- **Environment**: Node.js
- **Purpose**: Modern chat interface with tool integration

### 🏗️ Mnemoverse Arch (`mnemoverse-arch/`)
- **Technology**: Python + LangGraph + Mem0
- **Package Manager**: pip
- **Commands**: `python main.py`, development scripts
- **Environment**: Python virtual environment
- **Purpose**: Multi-agent orchestration system with persistent memory

### 🎮 Unity Prototype (`Unity-Prototype/`)
- **Technology**: Unity 3D + C#
- **Package Manager**: Unity Package Manager
- **Commands**: Open in Unity Editor
- **Environment**: Unity 2022.3 LTS
- **Purpose**: 3D spatial memory prototype

## 🛠️ Common Operations

### Multi-Repository Setup
```bash
# From root directory
npm run install:all  # Install all dependencies
npm run docs:dev     # Start docs development
npm run web:dev      # Start web client development
```

### Development Workflow
```bash
# Documentation work
cd mnemoverse-docs/
npm run docs:dev

# MCP Server development
cd mnemoverse-docs/mcp-server/
npm run dev

# Web client work  
cd mnemoverse-web-client/
npm run dev

# Chat UI work
cd mnemoverse-chat-ui/
npm run dev

# Research library work
cd mnemoverse-research-library/
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python services/source/main.py

# Multi-agent architecture work
cd mnemoverse-arch/
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python main.py
```

## 🎯 Project Context

### Current Phase: MCP Infrastructure & Agent Systems
- **Primary Focus**: Multi-agent orchestration and MCP ecosystem development
- **Active Development**: `mnemoverse-arch/`, `mnemoverse-chat-ui/`, `mnemoverse-docs/mcp-server/`
- **Production Ready**: `@mnemoverse/mcp-docs-server`, Research Library
- **Stable**: `mnemoverse-web-client/` (minimal maintenance)
- **Experimental**: `Unity-Prototype/` (future development)

### Key Achievements
1. **Published MCP Server**: `@mnemoverse/mcp-docs-server` on npm
2. **Research Infrastructure**: 300+ curated AI research sources
3. **Agent Memory Systems**: LangGraph + Mem0 integration
4. **Universal Tool Access**: MCP coordination protocols

### Key Principles
1. **Agent-First Design**: All systems optimized for AI agent interaction
2. **Clean Architecture**: Separation of concerns, dependency injection
3. **Provider-Agnostic**: Easy switching between services (OpenAI/Ollama, etc.)
4. **Documentation-First**: Comprehensive docs for every component
5. **Open Source Ready**: Public packages and community engagement

## 🚫 Common Mistakes to Avoid

1. **Wrong Package Manager**: 
   - ❌ `pip install` in Node.js repos
   - ❌ `npm install` in Python repos

2. **Wrong Directory**:
   - ❌ Running Python commands from root
   - ❌ Running npm commands in wrong subfolder

3. **Mixed Environments**:
   - ❌ Using same virtual environment for different projects
   - ❌ Installing global dependencies instead of project-specific

4. **Ignoring Repository Context**:
   - ❌ Creating Python files in Node.js repos
   - ❌ Creating Node.js configs in Python repos

## 📋 Quick Reference

### File Indicators
- `package.json` → Node.js repository (use npm)
- `requirements.txt` → Python repository (use pip + venv)
- `Assets/` folder → Unity repository (use Unity Editor)
- `.md` files in `docs/` → Documentation repository
- `mcp-server/` folder → MCP server development
- `next.config.ts` → Next.js application (chat-ui)
- `langgraph` in requirements → Multi-agent system (mnemoverse-arch)

### Command Patterns
```bash
# Always check where you are
pwd

# Navigate to correct repository first
cd mnemoverse-docs/          # For documentation work
cd mnemoverse-web-client/    # For web client work  
cd mnemoverse-research-library/  # For research library work
cd mnemoverse-chat-ui/       # For chat interface work
cd mnemoverse-arch/          # For multi-agent system work

# Use appropriate package manager
npm install    # In Node.js repos
pip install    # In Python repos (with venv active)

# MCP Server specific
cd mnemoverse-docs/mcp-server/  # For MCP server development
npm run dev    # Start MCP server in development mode
```

## 🔗 Cross-Repository References

When working across repositories, remember:
- Each repo has its own `.github/copilot/instructions.md` with specific details
- Root repo coordinates but doesn't contain implementation
- Changes in one repo may require updates in others (documentation, APIs)

**Always consult the specific repository's instructions for detailed guidance!**
