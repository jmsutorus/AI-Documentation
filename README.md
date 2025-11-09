# AI-Documentation

Context Pipeline Engineering Workflow for AI-assisted software development.

## Overview

This repository contains the configuration and documentation for a structured workflow that leverages AI agents to implement features with high quality, comprehensive testing, and full documentation.

## Context Pipeline Engineering Workflow

This workflow ensures features are planned, implemented, tested, and documented systematically with AI assistance.

### 1. Create PRD Document
Define the feature with a Product Requirements Document (PRD) that includes:
- Feature description and objectives
- Acceptance criteria
- Success metrics

### 2. Create Context Document
Build a context document with references to implementation examples:
- Links to similar implementations in the codebase
- Example files (e.g., "See `examples/table-example.tsx` for table implementation patterns")
- Relevant documentation and best practices

### 3. Run `web-research-specialist` Agent
Search the web and codebase for additional context:
```
Use the web-research-specialist agent to gather implementation examples and best practices
```
This agent researches:
- Similar implementations in open source projects
- Community best practices and patterns
- Technical documentation and guides

### 4. Run `plan-reviewer` Agent
Validate the plan and identify gaps:
```
Use the plan-reviewer agent to analyze the implementation plan
```
The agent checks for:
- Missing considerations or edge cases
- Potential issues or risks
- Alternative approaches

### 5. Run `/dev-docs` Command
Generate comprehensive planning documentation:
```
/dev-docs [feature description]
```
This creates:
- Detailed implementation plan
- Context and reference documents
- Task list for execution

### 6. Run `/execute-plan` Command
Execute the plan step-by-step:
```
/execute-plan [plan name]
```
Systematically implements the feature according to the documented plan.

### 7. Run `change-code-reviewer` Agent
Analyze code quality and identify issues:
```
Use the change-code-reviewer agent to review recent changes
```
Reviews for:
- Type errors and runtime errors
- Security vulnerabilities
- Logic flaws and bugs
- Code quality and refactoring opportunities

### 8. Run `test-writer` Agent
Write comprehensive unit tests:
```
Use the test-writer agent to create tests for the implementation
```
Ensures:
- 90%+ test coverage
- All tests pass
- Edge cases and error scenarios covered

### 9. Run `task-final-review` Agent
Validate against PRD requirements:
```
Use the task-final-review agent to perform final validation
```
Verifies:
- All PRD requirements are met
- Feature works as specified
- All tests pass
- Implementation is ready for production

### 10. Run `/gen-commit-msg` Command
Create commit message and push for PR:
```
/gen-commit-msg
```
Prepares code for pull request review.

### 11. Run `/dev-docs-update` Command
Update documentation with implementation details:
```
/dev-docs-update
```
Documents what was implemented and any learnings.

## Directory Structure

```
.claude/
├── agents/           # Custom AI agent definitions
├── commands/         # Slash command definitions
└── CLAUDE.md         # Project-specific instructions for Claude

dev/
└── active/          # Active development plans and PRDs

examples/            # Reference implementations
```

## Available Agents

- **web-research-specialist**: Research implementations and best practices
- **plan-reviewer**: Validate plans and identify gaps
- **change-code-reviewer**: Review code for errors and quality issues
- **test-writer**: Write comprehensive tests with 90%+ coverage
- **task-final-review**: Final validation against requirements
- **code-refactor-master**: Refactor code for better organization
- **documentation-architect**: Create and update documentation

## Benefits

This workflow provides:
- **Consistency**: Standardized approach to feature development
- **Quality**: Multiple review stages catch issues early
- **Documentation**: Comprehensive documentation at every stage
- **Testing**: High test coverage with automated test generation
- **Traceability**: Clear connection from requirements to implementation
