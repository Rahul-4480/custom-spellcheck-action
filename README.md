# Spell Check and Grammar Check GitHub Action

This GitHub Action checks spelling and grammar in markdown files, leveraging OpenAI GPT-4, and posts comments directly on pull requests highlighting the issues found.

## Usage

To use this action in your workflow, add the following step to your `.github/workflows/spell_check.yml` file:

```yaml
jobs:
  spellcheck:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Run Spell Check
        uses: your-github-username/spell-check-action@v1
        with:
          openai_api_key: ${{ secrets.OPENAI_API_KEY }}
          github_token: ${{ secrets.GITHUB_TOKEN }}
          pr_number: ${{ github.event.number }}
          files: 'blogs/file1.md, blogs/file2.md'  # Specify files to check
