## AP-02: Not stating what the software should AND should not do

**What it means:** A spec that only says what a feature does leaves developers (and AI agents) to fill in the blanks. Everyone fills them in differently, and agents expand scope by default.

**What a good spec includes:**
- Explicit "should NOT" statements for key features (e.g., "users cannot upload .exe files", "file size limit is 5MB")
- Out-of-scope features written down as exclusions, not just left out
- Hard "never" rules and boundaries stated as first-class requirements
