# Delegation Playbook -- Real-World Examples

This playbook provides concrete examples of how to delegate common lightweight tasks using the OpenRouter MCP tools. Each example shows the exact tool call parameters.

---

## Example 1: Rename a Sidebar Label

**User Request**: "Rename 'NPS Portfolio' to 'NPS' in the sidebar"

**Classification**: TIER 2 -- Text/Label Changes

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_code_task"
Arguments: {
  "task": "Find the text 'NPS Portfolio' in the sidebar navigation items and rename it to 'NPS'. Do not change anything else.",
  "file_path": "C:\\Users\\Vijay Pai\\MyData\\Projects\\ladder\\src\\components\\Sidebar.jsx",
  "file_content": "<full content of Sidebar.jsx>",
  "language": "javascript"
}
```

---

## Example 2: Change a CSS Color

**User Request**: "Make the active sidebar highlight blue instead of green"

**Classification**: TIER 2 -- CSS/Styling

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_code_task"
Arguments: {
  "task": "Change the active sidebar navigation item highlight color from green (any green variant) to blue. Update both the text color and background color classes. Look for classes like text-green-400, bg-green-600/10 and change them to text-blue-400, bg-blue-600/10.",
  "file_path": "C:\\Users\\Vijay Pai\\MyData\\Projects\\ladder\\src\\components\\Sidebar.jsx",
  "file_content": "<full content of Sidebar.jsx>",
  "language": "javascript"
}
```

---

## Example 3: Update CHANGELOG Entry

**User Request**: "Add a changelog entry for v3.5.0 about the new watchlist feature"

**Classification**: TIER 2 -- Documentation

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_doc_task"
Arguments: {
  "task": "Add a new entry at the top of the changelog for version 3.5.0 dated 2026-08-17. The entry should describe: Added Watchlist feature with real-time price alerts, custom alert thresholds, and notification badges in the sidebar. Follow the existing changelog format exactly.",
  "existing_content": "<full content of CHANGELOG.md>",
  "context": "Project: Ladder - Institutional Finance & Investment Dashboard. Uses semantic versioning. No emojis or emoticons in documentation."
}
```

---

## Example 4: Fix Number Formatting

**User Request**: "Change all money values to show exactly 2 decimal places"

**Classification**: TIER 2 -- Formatting/Precision

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_code_task"
Arguments: {
  "task": "In the formatMoney function, ensure all formatted numbers always display exactly 2 decimal places. Set minimumFractionDigits: 2 and maximumFractionDigits: 2 in all toLocaleString calls.",
  "file_path": "C:\\Users\\Vijay Pai\\MyData\\Projects\\ladder\\src\\context\\ThemeAuthContext.jsx",
  "file_content": "<full content of ThemeAuthContext.jsx>",
  "language": "javascript"
}
```

---

## Example 5: Swap an Icon

**User Request**: "Change the Dividends icon from DollarSign to Coins"

**Classification**: TIER 2 -- Icon/Badge Swap

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_code_task"
Arguments: {
  "task": "In the sidebar navigation items array, find the Dividends menu item and change its icon from DollarSign to Coins. Also update the Lucide import at the top of the file to import Coins instead of DollarSign (if DollarSign is not used elsewhere).",
  "file_path": "C:\\Users\\Vijay Pai\\MyData\\Projects\\ladder\\src\\components\\Sidebar.jsx",
  "file_content": "<full content of Sidebar.jsx>",
  "language": "javascript"
}
```

---

## Example 6: Add a Column to a Database Table

**User Request**: "Add a 'notes' TEXT column to the holdings table"

**Classification**: TIER 2 -- Mechanical SQL

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_code_task"
Arguments: {
  "task": "Write an ALTER TABLE SQL statement to add a 'notes' column of type TEXT (nullable) to the 'holdings' table. Return only the SQL statement.",
  "file_path": "migration.sql",
  "file_content": "-- Migration file",
  "language": "sql"
}
```

---

## Example 7: Add Status Filter Tabs (Pattern Replication)

**User Request**: "Add Active/Exited/All filter tabs to NpsView like we have in IndianStocksView"

**Classification**: TIER 2 -- Pattern Replication

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_code_task"
Arguments: {
  "task": "Add status filter tabs (Active Positions, Fully Exited, All Data) to this NPS view component. The tabs should filter the holdings array based on the 'status' field. Use the same tab styling and state management pattern as shown in the context.",
  "file_path": "C:\\Users\\Vijay Pai\\MyData\\Projects\\ladder\\src\\views\\NpsView.jsx",
  "file_content": "<full content of NpsView.jsx>",
  "context": "PATTERN TO FOLLOW (from IndianStocksView.jsx):\n<relevant excerpt showing the tab implementation in IndianStocksView>",
  "language": "javascript"
}
```

---

## Example 8: Remove Clutter / Clean Up UI

**User Request**: "Remove the subtitle 'Daily gains & losses heatmap' from CalendarView"

**Classification**: TIER 2 -- Text/Label Changes

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_code_task"
Arguments: {
  "task": "Remove the subtitle text 'Daily gains & losses heatmap' and its containing element from the page header. Do not remove the main title.",
  "file_path": "C:\\Users\\Vijay Pai\\MyData\\Projects\\ladder\\src\\views\\CalendarView.jsx",
  "file_content": "<full content of CalendarView.jsx>",
  "language": "javascript"
}
```

---

## Example 9: LADDER.MD Changelog Entry

**User Request**: "Update LADDER.MD with the changes we just made"

**Classification**: TIER 2 -- Documentation

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_doc_task"
Arguments: {
  "task": "Add a new row to the Change Log & Maintenance History table. Version: v3.5.0, Date: 2026-08-17, Description: Added Watchlist feature with real-time price alerts and notification badges. Author: Antigravity AI. Follow the exact table format of existing entries.",
  "existing_content": "<full content of LADDER.MD>",
  "context": "The table uses this format: | **vX.X.X** | YYYY-MM-DD | Description | Author |"
}
```

---

## Example 10: .gitignore Addition

**User Request**: "Add .env.local to the gitignore"

**Classification**: TIER 2 -- Config Edit

**MCP Tool Call**:
```
ServerName: "openrouter-delegate"
ToolName: "delegate_code_task"
Arguments: {
  "task": "Add '.env.local' to this .gitignore file. Place it near the existing .env entry if one exists.",
  "file_path": "C:\\Users\\Vijay Pai\\MyData\\Projects\\ladder\\.gitignore",
  "file_content": "<full content of .gitignore>",
  "language": "text"
}
```

---

## Anti-Patterns: Do NOT Delegate These

| Task | Why Not |
|:---|:---|
| "Build a new Watchlist feature" | Architecture design + multiple new files |
| "Fix the XIRR calculation bug" | Complex algorithm debugging |
| "Integrate a new API for crypto prices" | API design + error handling + new service |
| "Redesign the theme system" | Cross-cutting CSS architecture |
| "Optimize dashboard load performance" | Profiling + multi-file optimization |
| "Add user authentication with OAuth" | Security architecture + multi-file |
