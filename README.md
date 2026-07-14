# GitHub Bounty Hunter

Automated tool that searches GitHub for issues with monetary bounties, analyzes them using OpenAI, generates fix code, and submits Pull Requests to earn rewards.

## Features

- **Smart Search** - 7 query combinations covering bounty labels, help-wanted tags, and dollar-amount patterns
- **Bounty Detection** - Extracts amounts in USD, ETH, USDC, USDT from issue text
- **AI-Powered Analysis** - Uses OpenAI GPT-4o to analyze issues and generate fixes
- **Automated PRs** - Fork, branch, commit, and PR creation via GitHub API
- **Safety First** - Dry-run mode, rate-limit awareness, duplicate PR detection, exponential backoff

## Quick Start

```bash
# Set credentials
export GITHUB_TOKEN="ghp_xxx"
export OPENAI_API_KEY="sk-xxx"

# Install dependencies
pip install -r requirements.txt

# Dry-run (safe, no PRs created)
python github_bounty_hunter.py --dry-run --limit 3

# Live run
python github_bounty_hunter.py --limit 5

# Target a specific issue
python github_bounty_hunter.py --issue https://github.com/owner/repo/issues/123

# Filter by minimum bounty
python github_bounty_hunter.py --min-bounty 50
```

## Requirements

- Python 3.9+
- GitHub Personal Access Token (with `repo` and `read:user` scopes)
- OpenAI API Key

## ⚠️ Important Warning

Automated PR submissions may be perceived as spam by repository maintainers. Always:
1. Start with --dry-run mode
2. Review generated code in outputs/ before submitting
3. Read each repository's CONTRIBUTING.md before contributing
4. Use responsibly and ethically

## License

MIT - see [LICENSE](LICENSE) file for details.
