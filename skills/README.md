# CNCF TOC Skills

This directory contains agent skills in support of the TOC's work.

## What are Skills?

Skills are reusable agent capabilities that help automate and standardize TOC workflows. Each skill provides:

- **Clear instructions** for when and how to use it
- **Consistent patterns** across TOC member workflows
- **Platform-agnostic guidance** that works with multiple AI tools
- **CNCF branding** and best practices built-in

## Available Skills

### [marp-presentation](./marp-presentation/)

Create professional slide deck presentations from markdown using Marp with CNCF branding.

**Use for:**
- TOC meeting presentations
- Project due diligence reviews
- TAG liaison updates
- Annual reports

## Skill Structure

Each skill follows the [AgentSkills.io](https://agentskills.io/) standard:

```
skill-name/
├── SKILL.md                      # Main skill documentation
├── customized/
│   └── config.example.yaml       # Configuration schema
├── references/
│   └── example.md                # Working examples
└── themes/                       # Brand assets (if applicable)
```

## Using Skills

Skills are designed to be used by AI coding assistants (Claude, Cursor, GitHub Copilot, etc.) or directly by TOC members.

### With AI Assistants

1. Point your AI assistant to the skill directory
2. Ask it to use a specific skill: "Create a presentation using the marp-presentation skill"
3. The assistant will follow the skill's instructions and apply CNCF branding

### Manually

Each skill's `SKILL.md` file contains complete instructions for manual use.

## Contributing

To propose a new skill:

1. Open an issue in [cncf/toc](https://github.com/cncf/toc/issues) with the `skill-proposal` label
2. Describe the workflow you want to standardize
3. Provide examples of current manual process
4. Wait for TOC approval before submitting a PR

### Skill Requirements

- Must support a TOC-specific workflow
- Should include CNCF branding where applicable
- Must follow AgentSkills.io standard format
- Needs working examples in `references/`
- Should be platform-agnostic (work with multiple AI tools)

## Questions?

- **TOC GitHub Issues:** https://github.com/cncf/toc/issues
- **TOC Mailing List:** cncf-toc@lists.cncf.io
