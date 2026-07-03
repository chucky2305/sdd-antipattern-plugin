## AP-07: Not mentioning constraints and assumptions

**What it means:** Developers (and AI agents) make decisions based on unstated assumptions. When those assumptions are wrong, things break at the worst possible time.

**What a good spec includes:**
- A "Constraints & Assumptions" section listing: technical environment, expected user behavior, data shape, scale, language, connectivity, browser/OS support, third-party API limits, performance requirements
- Connections to external services (APIs, databases, third-party tools) explicitly listed as constraints, including their limits and failure modes
