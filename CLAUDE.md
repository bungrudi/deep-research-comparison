# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

Compare deep research quality across three web-based deep research agents:
- **Gemini Web Deep Research** (via Chrome automation with `/gemini-research`)
- **ChatGPT Web Deep Research** (via Chrome automation with `/chatgpt-research`)
- **Super Grok Heavy Web Deep Research** (via Chrome automation with `/supergrok-research`)

## Workflow

The project follows a multi-phase pipeline:

### Phase 1: Rubric Design (Panel Debate)
A panel of three AI models debates to produce a scoring rubric:
- **Opus 4.6** (native Claude Code model)
- **Gemini 3.1 Pro** (via `/gemini-thinking-partner` skill, direct API)
- **GPT 5.4** (via `/opencode-brainstorm` skill)

The panel engages in multi-round structured debate to converge on evaluation criteria. Rubric output is saved locally.

### Phase 2: Topic Selection (Same Panel)
The same panel debates and selects the deep research topic(s) to be tested.

### Phase 3: Research Execution (Parallel Multi-Tab)
Run the chosen topic through all three deep research agents using **parallel multi-tab dispatch**:

1. Create 3 Chrome tabs (one per agent: Gemini, ChatGPT, Grok)
2. Navigate and submit the research prompt in each tab sequentially (~30s each)
3. All three deep research processes run **in parallel server-side** in the browser
4. Poll each tab periodically to detect completion
5. Extract and save results from each tab

**Do NOT use the self-contained skills** (`/gemini-research`, `/chatgpt-research`, `/supergrok-research`) for parallel runs — they block until completion. Instead, handle browser automation directly via `mcp__claude-in-chrome__*` tools with explicit `tabId` targeting.

```
Tab A (Gemini)  : [dispatch] =====[processing]======> [collect]
Tab B (ChatGPT) :    [dispatch] ==[processing]======> [collect]
Tab C (Grok)    :       [dispatch] [processing]======> [collect]
                 |--~2min--|------~10min parallel-----|--~3min--|
```

**Parallelism in other phases:** Panel debate (Phase 1-2) can also parallelize since Opus is native, Gemini uses API, and GPT uses OpenCode CLI — none of these compete for the browser.

### Phase 4: Scoring & Comparison
Load all three research outputs and score them against the rubric. Generate a comparison report.

## Directory Structure Convention

```
rubric/           — Rubric drafts and final rubric from panel debate
topics/           — Selected research topics
results/          — Raw research outputs from each agent
  gemini/
  chatgpt/
  grok/
scoring/          — Scoring results and comparison reports
```

## Key Skills Used

| Skill | Purpose | Notes |
|-------|---------|-------|
| `/gemini-research` | Gemini Deep Research (end-to-end) | Use only for single/standalone runs |
| `/chatgpt-research` | ChatGPT Deep Research (end-to-end) | Use only for single/standalone runs |
| `/supergrok-research` | Grok Heavy Deep Research (end-to-end) | Use only for single/standalone runs |
| `/gemini-thinking-partner` | Gemini 3.1 Pro for panel debate | Direct API, no browser needed |
| `/opencode-brainstorm` | GPT 5.4 for panel debate | OpenCode CLI, no browser needed |

## Multi-Tab Browser Automation

When running parallel research, manage tabs directly:

```
# 1. Load tools first
ToolSearch: select:mcp__claude-in-chrome__tabs_context_mcp
ToolSearch: select:mcp__claude-in-chrome__tabs_create_mcp
ToolSearch: select:mcp__claude-in-chrome__navigate
ToolSearch: select:mcp__claude-in-chrome__computer
ToolSearch: select:mcp__claude-in-chrome__get_page_text

# 2. Get context, create tabs
tabs_context_mcp → get existing tabs
tabs_create_mcp × 3 → get tabId for each agent

# 3. For each tab: navigate → interact → submit prompt
navigate(tabId=A, url="gemini.google.com") → submit research
navigate(tabId=B, url="chatgpt.com") → submit research
navigate(tabId=C, url="x.com/i/grok") → submit research

# 4. Poll: screenshot each tab to check completion status
# 5. Collect: get_page_text(tabId=X) for each completed tab
```

Every `mcp__claude-in-chrome__*` tool accepts a `tabId` — always pass it explicitly to target the correct tab.

## Important Constraints

- All Chrome browser tools must be loaded via `ToolSearch` before first use
- Tool calls are sequential, but research processes run in parallel in the browser
- For parallel dispatch, use direct browser automation — not the end-to-end skills
- Always save raw research output with full citations before scoring
- Panel debate should have explicit rounds with clear positions before converging
