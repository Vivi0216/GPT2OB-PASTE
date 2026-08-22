# Obsidian Paste Refiner

An Obsidian plugin for cleaning up Markdown pasted from ChatGPT and other AI tools.

## Features

- Fixes common ChatGPT/AI math export forms, including `\\( ... \\)`, `\\[ ... \\]`, math-like bracket blocks, and simple blocks such as `[ S ]` / `[ 3S ]`.
- Converts standalone Markdown horizontal rules from `---` to `***` while protecting YAML frontmatter, fenced code blocks, display math, and Setext headings.
- Reduces redundant blank lines.
- Keeps a required blank line after blockquotes/callouts so following prose is not swallowed by Markdown lazy continuation.
- Keeps table boundaries safe.
- Does **not** force blank lines before or after display-math blocks.
- Does **not** force blank lines before or after `***` horizontal rules.
- Leaves fenced code blocks untouched by math conversion.

## Blank-line modes

- **Gradual**: removes one blank line from each run per invocation.
- **Strict**: collapses ordinary repeated blank lines to one, while still removing blank lines directly around display-math fences and `***` horizontal rules when Markdown structure does not require them.

## Install manually

Copy this folder to:

`.obsidian/plugins/paste-refiner/`

Then reload Obsidian or disable/re-enable **Paste Refiner**.

The command is **Refine pasted content**.

## Credits

This project merges and adapts code from two MIT-licensed Obsidian plugins:

- Riverise/obsidian-paste-polish
- loglux/fix-math-for-obsidian

See `THIRD_PARTY_NOTICES.md` for the original copyright and license notices.
