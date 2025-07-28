# Contributing to Mnemoverse

Thank you for your interest in contributing to Mnemoverse! We're building the cognitive layer for AI agents and welcome contributors from all backgrounds.

## 🏗️ Multi-Repository Structure

Mnemoverse is organized as multiple specialized repositories. Choose based on your interests:

- **🌐 [mnemoverse-web-client](https://github.com/mnemoverse/mnemoverse-web-client)** - Landing page (Vite + JavaScript)
- **📚 [mnemoverse-docs](https://github.com/mnemoverse/mnemoverse-docs)** - Documentation & MCP server (VitePress + TypeScript)
- **🔬 [mnemoverse-research-library](https://github.com/mnemoverse/mnemoverse-research-library)** - AI research database (Python + FastAPI)
- **💬 [mnemoverse-chat-ui](https://github.com/mnemoverse/mnemoverse-chat-ui)** - Chat interface (Next.js + assistant-ui)
- **🏗️ [mnemoverse-arch](https://github.com/mnemoverse/mnemoverse-arch)** - Multi-agent orchestration (LangGraph + Mem0)

## Ways to Contribute

### 🐛 Report Bugs
- Check if the issue already exists in the relevant repository
- Use the appropriate bug report template
- Include steps to reproduce and system information
- Specify which repository and component is affected

### 💡 Suggest Features
- Review our [roadmap](https://mnemoverse.org/docs/roadmap) and existing issues
- Propose features in the most relevant repository
- Describe the problem it solves for AI agents or developers
- Consider how it fits with our agent-first design philosophy

### 📝 Improve Documentation
- Fix typos and improve clarity in [mnemoverse-docs](https://github.com/mnemoverse/mnemoverse-docs)
- Add examples for MCP server integration
- Expand research library categorization
- Write tutorials for agent development

### 💻 Submit Code
1. **Choose the right repository** for your contribution
2. **Fork the repository** and clone it locally
3. **Set up the development environment** (see repository-specific README)
4. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
5. **Follow coding standards** specific to each repository
6. **Write tests** where applicable
7. **Commit your changes** with clear messages
8. **Push to your fork** (`git push origin feature/amazing-feature`)
9. **Open a Pull Request** with detailed description

## Development Guidelines

### Code Style by Repository
- **Node.js repos** (docs, web-client, chat-ui): ESLint + Prettier, TypeScript preferred
- **Python repos** (research-library, mnemoverse-arch): Black + isort, type hints required
- **All repos**: Clear naming, self-documenting code, comprehensive tests

### Our Core Values
- **🧠 Cognitive Truth**: Model how minds actually work, not how we think they should
- **⚡ Radical Simplicity**: Every feature must justify its complexity
- **🤖 Agent-First**: Built for AI agents, adapted for humans
- **🔓 Open by Default**: Cognitive models and protocols are open source

### AI Agent Considerations
When contributing, remember our agent-first design:
- APIs should be easily consumable by AI agents
- Documentation should be structured for semantic understanding
- Tool interfaces should follow MCP standards where applicable
- Consider how features improve agent context and memory

## Repository-Specific Setup

### Node.js Repositories
```bash
npm install
npm run dev  # or specific commands in package.json
```

### Python Repositories  
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
python main.py  # or specific entry point
```

## Testing

- **Unit tests**: Required for new features
- **Integration tests**: For API endpoints and core workflows
- **Documentation tests**: Ensure examples work as written
- **MCP compliance**: For server implementations

## Pull Request Process

1. **Title**: Clear, descriptive title with repository context
2. **Description**: 
   - What does this PR do?
   - Why is this change needed?
   - How does it work?
   - Any breaking changes?
3. **Testing**: How was this tested?
4. **Documentation**: Updated relevant docs?
5. **Agent Impact**: How does this affect AI agent usage?

## Community Guidelines

### Be Respectful
- Constructive feedback only
- Assume good intentions
- Help others learn and grow

### Focus on Impact
- Prioritize agent experience improvements
- Consider long-term maintainability  
- Think about cognitive load on users

### Stay Aligned
- Follow our architectural principles
- Maintain consistency across repositories
- Consider the bigger picture

## Getting Help

- **Documentation**: [mnemoverse.org/docs](https://mnemoverse.org/docs)
- **MCP Server**: Try `@mnemoverse/mcp-docs-server` in your IDE
- **Issues**: Search existing issues in relevant repositories
- **Discussions**: Use GitHub Discussions for questions

## Recognition

Contributors are recognized in:
- Repository README files
- Release notes for significant contributions
- Our [contributors page](https://mnemoverse.org/contributors)

Thank you for helping build the cognitive layer for AI agents! 🧠🤖

### Commit Messages
- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less

## Community

- Join our [Discord](https://discord.gg/mnemoverse)
- Follow us on [Twitter](https://twitter.com/mnemoverse)
- Read our [blog](https://mnemoverse.com/blog)

## License

By contributing, you agree that your contributions will be licensed under the same license as the project.