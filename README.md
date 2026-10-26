# AI Course SG — MCP Server

Free Model Context Protocol server exposing Singapore's complete AI course market:
**530 live courses across 16 providers**, with SkillsFuture net-fee computation and
market statistics. Endpoint: `https://aicourse.com.sg/api/mcp`

Listed on: [aicourse.com.sg/connect](https://aicourse.com.sg/connect)

## What it does

- Search the full Singapore AI course directory (all providers, filters by industry/technology/job function)
- Compute subsidised net course fees per learner profile (SkillsFuture Credit, mid-career top-ups, UTAP, SFEC)
- Retrieve market statistics (fee transparency, median prices) — citable, refreshed daily

## Why

Singapore's AI training market is opaque: only ~20% of providers publish fees. This server
makes the whole market machine-readable so AI assistants can give grounded, verifiable
answers instead of guesses.

## Status

Public, read-only, no auth. Point any MCP client at `https://aicourse.com.sg/api/mcp`.
