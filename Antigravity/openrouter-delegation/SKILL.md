---
name: openrouter-delegation
description: "Automatically classifies coding tasks into tiers and delegates lightweight tasks to free OpenRouter models via MCP server, preserving premium model rate limits for heavy-lifting architectural work, research, and complex algorithms."
---

# OpenRouter Task Delegation Skill

## Purpose

This skill enables automatic and manual delegation of lightweight coding tasks to **free OpenRouter AI models** via the `openrouter-delegate` MCP server. Premium Antigravity model capacity is preserved for work that genuinely requires deep reasoning, architectural design, and multi-file orchestration.

---

## MANDATORY: Task Classification Protocol

When ANY coding request is received, you MUST follow this protocol:

### Step 1: Check for Manual Override Keywords

Scan the user's message for explicit routing instructions:

| User Keyword | Action |
|:---|:---|
| "delegate this", "use openrouter", "use free model", "route to openrouter" | Force TIER 2 (delegate to OpenRouter) regardless of complexity |
| "handle this yourself", "use premium", "don't delegate", "do this yourself" | Force TIER 1 (use Antigravity directly) regardless of simplicity |
| No keyword present | Proceed to automatic classification (Step 2) |

### Step 2: Automatic Classification

If no manual override keyword is detected, classify the task using the matrices below.

---

## TIER 1: Antigravity Premium Model (Handle Directly)

Use your own capabilities for tasks matching ANY of these categories:

### Architecture & Design
- New component architecture or state management design
- Database schema design (DDL, triggers, RLS policies, migrations)
- API endpoint design with complex business logic
- Cross-cutting system refactors (theme systems, auth, global state)

### Planning & Research
- Creating implementation plans (`implementation_plan.md`)
- Creating task lists (`task.md`)
- Research and analysis (reading documentation, comparing approaches)
- Reading and understanding `LADDER.MD` or project context files

### Complex Algorithms & Logic
- Financial computations (XIRR, FIFO, P&L, currency conversion)
- Mathematical algorithms (Newton-Raphson, time-series analysis)
- Complex data transformations and pipeline design
- Batch ingestion scripts with business rule enforcement

### Multi-File Orchestration
- Changes spanning 3 or more interdependent files
- Adding new features that require frontend + backend + database changes
- Refactoring that cascades across multiple components

### Complex Debugging
- Investigating bugs with unclear root cause
- Race conditions, state management issues
- Performance optimization requiring profiling and analysis

### Design System Work
- Creating new design token architectures
- Building new theme variants with deep CSS variable chains
- Designing animation systems or interaction patterns

---

## TIER 2: OpenRouter Free Model (Delegate via MCP)

Delegate to OpenRouter for tasks matching ANY of these categories:

### CSS & Styling (Single File)
- Color changes, spacing adjustments, font updates
- Border radius, box shadow, opacity tweaks
- Adding/removing CSS classes
- Responsive breakpoint adjustments
- Theme variable value changes (not architecture changes)

### Text & Label Changes
- Renaming labels, button text, page titles, placeholder text
- Updating static strings, tooltips, aria-labels
- Fixing typos in code or comments

### Documentation
- CHANGELOG.md updates (version entries)
- README.md section additions or edits
- LADDER.MD changelog table entries
- Inline code comments and JSDoc
- Commit message generation

### Simple Component Edits
- Adding/removing/changing component props
- Changing default parameter values
- Swapping Lucide icon names
- Updating badge text or status labels
- Changing number formatting (decimal places, locale)
- Date format changes

### Config & Environment
- `.env` value changes
- `package.json` field updates
- `.gitignore` additions
- `vite.config.js` or `tailwind.config.js` tweaks

### Mechanical SQL
- ALTER TABLE add/drop column
- Simple INSERT, UPDATE, DELETE statements
- Index creation
- Constraint additions/removals

### Pattern Replication
- Adding status filter tabs to a new view (copy pattern from existing)
- Adding sort controls (copy pattern from existing)
- Creating a new view file that closely follows an existing template
- Extending an existing pattern to a new component

### Simple Bug Fixes
- Missing import statements
- Off-by-one errors with clear root cause
- Null/undefined checks
- Incorrect prop names or types
- Missing closing tags or brackets

### Git Operations
- Generating commit messages
- Branch naming suggestions

---

## Delegation Workflow

When a task is classified as TIER 2, follow these exact steps:

### Step 1: Announce Classification
Tell the user:
```
[TIER 2 - Delegating to OpenRouter] Category: <category name>
Task: <brief description>
```

### Step 2: Read Target File
Use `view_file` to read the complete content of the file to be edited.

### Step 3: Gather Context (if needed)
For tasks that require understanding project patterns:
- Read relevant sections of LADDER.MD
- Read relevant CSS tokens from index.css
- Read related component files for pattern reference

### Step 4: Call MCP Tool

For **code tasks**, call:
```
call_mcp_tool(
  ServerName: "openrouter-delegate",
  ToolName: "delegate_code_task",
  Arguments: {
    "task": "<specific description of the change>",
    "file_path": "<absolute file path>",
    "file_content": "<complete current file content>",
    "context": "<relevant context excerpts>",
    "language": "<javascript|css|markdown|json|sql>"
  }
)
```

For **documentation tasks**, call:
```
call_mcp_tool(
  ServerName: "openrouter-delegate",
  ToolName: "delegate_doc_task",
  Arguments: {
    "task": "<what documentation to write/update>",
    "existing_content": "<current doc file content>",
    "context": "<project context>"
  }
)
```

### Step 5: Validate Response
- Check if the response starts with `DELEGATION_FAILED:` -- if so, fall back to TIER 1
- Verify the returned code is syntactically valid
- Confirm only the requested changes were made (no unrelated modifications)
- If the result looks garbled or incomplete, fall back to TIER 1

### Step 6: Apply Changes
- Use `write_to_file` (Overwrite: true) to apply the complete file
- Or use `replace_file_content` if only a small section changed and you can extract it

### Step 7: Verify
- For frontend changes: check the browser if running
- For backend changes: test the API endpoint
- For docs: review formatting

### Step 8: Report
Tell the user:
```
[Completed via OpenRouter] Applied: <brief description of what changed>
```

---

## Fallback Rules

ALWAYS fall back to TIER 1 (handle directly) when:

1. The MCP tool returns `DELEGATION_FAILED:` error
2. The returned code appears garbled, truncated, or incorrect
3. The returned code contains unexpected changes beyond what was requested
4. The task turns out to be more complex than initially classified
5. You are uncertain about the classification -- **when in doubt, use TIER 1**

---

## Hybrid Approach for Forced Heavy Tasks

When the user forces a heavy task to OpenRouter (manual override), use this strategy:

1. **Break down** the heavy task into 3-5 smaller subtasks
2. **Prepare detailed context** for each subtask (file content + project patterns + design tokens)
3. **Delegate each subtask** individually via the MCP tool
4. **Validate and stitch** the results together
5. **Fix any issues** yourself (TIER 1) if subtask results conflict

---

## Important Notes

- Free models have a limit of **20 requests/minute** and **50 requests/day** (1,000/day after $10 lifetime spend)
- Each file edit counts as 1 request. Plan your delegations efficiently.
- The `openrouter/free` model auto-routes to the best available free model. The specific model may change day to day.
- If the MCP server is not running or not registered, all tasks default to TIER 1 silently.