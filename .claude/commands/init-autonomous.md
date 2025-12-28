# Initialize Autonomous Claude Project

Set up a new project with full autonomous Claude configuration.

## Instructions

Run this SINGLE compound command to set up everything at once (minimizes prompts):

```bash
mkdir -p .claude/hooks/ContextRecoveryHook .claude/hooks/SkillActivationHook .claude/skills .claude/rules .claude/commands .claude/backups && \
cp ~/.claude/settings.json .claude/ 2>/dev/null || true && \
cp ~/.claude/hooks/ContextRecoveryHook/*.mjs .claude/hooks/ContextRecoveryHook/ 2>/dev/null || true && \
cp ~/.claude/hooks/SkillActivationHook/*.mjs .claude/hooks/SkillActivationHook/ 2>/dev/null || true && \
cp ~/.claude/hooks/auto-git-workflow.mjs .claude/hooks/ 2>/dev/null || true && \
cp ~/.claude/skills/skill-rules.json .claude/skills/ 2>/dev/null || true && \
cp -r ~/.claude/skills/git-automation .claude/skills/ 2>/dev/null || true && \
cp -r ~/.claude/skills/session-management .claude/skills/ 2>/dev/null || true && \
cp -r ~/.claude/skills/code-review .claude/skills/ 2>/dev/null || true && \
cp -r ~/.claude/skills/testing .claude/skills/ 2>/dev/null || true && \
cp ~/.claude/rules/*.md .claude/rules/ 2>/dev/null || true && \
cp ~/.claude/commands/*.md .claude/commands/ 2>/dev/null || true && \
echo '{"autoCommit":true,"autoPush":false,"autoPR":false,"commitPrefix":"","branchPattern":"claude/{type}/{description}","protectedBranches":["main","master","production"]}' > .claude/git-automation.json && \
echo "Setup complete"
```

Then create CLAUDE.md using the directory name (DO NOT ask questions - use placeholders):

```markdown
# {directory-name}

## Project Overview
[Add project description]

## Tech Stack
[Add technologies used]

## Build/Test Commands
```bash
# Add build commands
# Add test commands
```

## Current Focus
- Project initialization complete
- Ready for autonomous development

---
*Inherits global autonomous configuration from ~/.claude/*
```

Finally, initialize git if not already a repo:
```bash
git rev-parse --git-dir >/dev/null 2>&1 || git init
```

Report success with available commands: /commit, /pr, /ship, /review, /status, /autonomous
