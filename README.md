# GPT2OB-PASTE

An Obsidian plugin for automatically refining Markdown pasted from ChatGPT, Codex, and other AI tools.

The plugin processes pasted text directly during Ctrl/Cmd+V, making AI-generated Markdown more compatible with Obsidian without modifying the system clipboard.

## Features

- Automatically refines text when pasted into Obsidian.
- Converts common LaTeX math delimiters to Obsidian-compatible formats:
  - `\( ... \)` → `$ ... $`
  - `\[ ... \]` → `$$ ... $$`
- Handles common AI-exported math formats and math-like bracket blocks.
- Preserves fenced code blocks and inline code during math conversion.
- Reduces redundant blank lines while preserving Markdown structure.
- Keeps necessary spacing around blockquotes, callouts, and tables.
- Optionally converts standalone horizontal rules from `---` to `***`.
- Leaves image and file pastes to Obsidian's native paste handling.
- Provides a manual `Refine pasted content` command for existing notes.

## Blank-line modes

Two blank-line cleanup modes are available:

- **Gradual**: removes one blank line from each repeated blank-line sequence per invocation.
- **Strict**: collapses repeated blank lines to a single blank line while preserving spacing required by Markdown structure.

Blank lines directly around display-math blocks and `***` horizontal rules are removed when they are not structurally required.

## Automatic paste refinement

Automatic refinement is enabled by default.

The typical workflow is:

`ChatGPT / Codex → Copy → Obsidian → Ctrl/Cmd+V`

The pasted text is refined before being inserted into the note.

This processing only occurs inside Obsidian. The Windows/macOS system clipboard itself is not modified, so pasting the same copied content into other applications remains unaffected.

Automatic paste processing can be enabled or disabled from the plugin settings.

## Math conversion

GPT2OB-PASTE converts AI-generated LaTeX delimiters into formats that Obsidian renders natively.

Examples:

Inline math:

`\(a+b=c\)` → `$a+b=c$`

Display math:

`\[a+b=c\]` → `$$a+b=c$$`

The plugin also includes additional safeguards and heuristics inherited and adapted from Fix Math for Obsidian for handling common AI-generated mathematical content.

Existing fenced code blocks are left untouched.

## Installation

### Manual installation

1. Download:
   - `main.js`
   - `manifest.json`
   - `styles.css` if included
2. Create the following folder inside the Obsidian vault:

   `.obsidian/plugins/gpt2ob-paste/`

3. Place the downloaded files in this folder.
4. Restart Obsidian, or reload the app.
5. Go to **Settings → Community plugins** and enable **GPT2OB-PASTE**.

## Manual command

In addition to automatic paste processing, the plugin provides:

`Refine pasted content`

Open the Obsidian Command Palette with `Ctrl/Cmd+P` to run it.

If text is selected, only the selected text is processed. Otherwise, the current note is processed.

## Credits

GPT2OB-PASTE is a fork and derivative work of:

- [Kai651111/obsidian-paste-refiner](https://github.com/Kai651111/obsidian-paste-refiner)

The upstream project merges and adapts code from:

- [Riverise/obsidian-paste-polish](https://github.com/Riverise/obsidian-paste-polish)
- [loglux/fix-math-for-obsidian](https://github.com/loglux/fix-math-for-obsidian)

These upstream projects are distributed under the MIT License.

The original copyright and license notices are retained in `LICENSE` and `THIRD_PARTY_NOTICES.md`.

## License

MIT License.

See `LICENSE` and `THIRD_PARTY_NOTICES.md` for details.
