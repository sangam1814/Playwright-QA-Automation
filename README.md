
## Overview
This project implements a semi-autonomous browser agent that can open a website, observe its state, make decisions at runtime, and interact with the page using heuristics and internal state.

The goal is not full automation, but to demonstrate reasoning, adaptability, and intelligent interaction with dynamic web pages.

## Problem Chosen
Websites change frequently and behave unpredictably. Traditional scripted automation often breaks.
This agent is designed to:
- Observe the page state
- Decide next actions dynamically
- Handle navigation, scrolling, and new tabs
- Avoid login/account flows
- Simulate human-like interaction timing

## Approach

The agent follows an Observe → Decide → Act loop:

1. **Observe**: Detect page URL, visible links, viewport, scroll position.
2. **Decide**: Choose action based on internal state (searched, scrolled, clicked, etc.).
3. **Act**: Perform search, scroll, click visible product, close new tab, restore state.

State is maintained across steps to avoid repetition and allow multi-step reasoning.

## Features
- Runtime decision making (not hardcoded script)
- State-based behavior
- New-tab handling and restoration
- Noise filtering (login, cart, privacy links ignored)
- Human-like delays
- Logs and step-by-step output

## Limitations
- Uses heuristics instead of true ML
- Website DOM changes may break selectors
- Not a full test framework

## Future Improvements
- Add visual detection (bounding box classification)
- Add LLM-based reasoning for decisions
- Add site-agnostic selectors
- Add structured issue detection

## How to Run

```bash
pip install playwright
playwright install
python agent.py
