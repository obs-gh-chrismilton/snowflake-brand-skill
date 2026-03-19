# Snowflake Brand Skill for Claude Code

A Claude Code plugin that provides official Snowflake brand guidelines, colors, typography, logos, and assets. When enabled, Claude Code automatically applies Snowflake's visual identity to any design, code, document, or presentation it generates.

## What It Does

When you ask Claude Code to build something Snowflake-branded — a web page, a Word document, a CSS stylesheet, a presentation, or partner materials — this skill gives it the official specs:

- **Color palette** (primary, secondary, tertiary with hex, RGB, CMYK, and Pantone values)
- **Typography** (TEXTA for headlines, Lato for body, with fallback guidance)
- **Logo usage rules** (clear space, background requirements, variant selection)
- **Button specifications** (dimensions, corner radius, font weight, character limits)
- **Co-branding and partner guidelines** (logo placement, sizing, alignment)
- **Data visualization color sequence** (ordered for maximum contrast)
- **Document and presentation formatting** (customer-facing and internal)

Without the skill, Claude uses generic colors and guesses at brand specs. With it, output is brand-compliant from the first draft.

## Installation

Add the plugin source and enable it in your Claude Code settings. Open `~/.claude/settings.json` and add (or merge with your existing config):

```json
{
  "enabledPlugins": {
    "snowflake-brand@obs-gh-chrismilton": true
  },
  "extraKnownMarketplaces": {
    "obs-gh-chrismilton": {
      "source": {
        "source": "github",
        "repo": "obs-gh-chrismilton/snowflake-brand-skill"
      }
    }
  }
}
```

Then restart Claude Code. The skill will be available automatically.

### Verify Installation

After installing, you can confirm the skill is loaded by running:

```
/skills
```

You should see `snowflake-brand` in the list. You can also test it:

```
What are Snowflake's official brand colors?
```

If the response includes specific hex codes (#29B5E8, #11567F, etc.) and names like "Snowflake Blue" and "Mid Blue," the skill is working.

## Usage

The skill triggers automatically when Claude Code detects Snowflake-related design work. You can also invoke it explicitly:

**Automatic triggers** — any of these will activate the skill:
- "Build a Snowflake-branded landing page"
- "Use Snowflake colors for this dashboard"
- "Create a customer-facing document with Snowflake branding"
- "What are Snowflake's brand colors?"
- "Add the Snowflake logo to this page"

**Explicit invocation:**
```
/snowflake-brand
```

### Example Prompts

```
Build a hero section for a Snowflake partner page with our logo and a CTA button.
```

```
Generate CSS variables for the full Snowflake color palette.
```

```
Create a Word document with Snowflake branding — use the right colors for headings, tables, and accents.
```

```
I'm building a co-branded page with Anthropic. How should the logos be arranged?
```

## Color Reference

### Primary Colors

| Name | Hex | Usage |
|------|-----|-------|
| Snowflake Blue | `#29B5E8` | Primary brand color, CTAs, links |
| Mid Blue | `#11567F` | Headings, hover states, depth |
| Midnight | `#000000` | Body text, high-contrast elements |

### Secondary Colors

| Name | Hex | Usage |
|------|-----|-------|
| Star Blue | `#71D3DC` | Light accents, secondary highlights |
| Valencia Orange | `#FF9F36` | Warm accents, alerts, emphasis |
| Purple Moon | `#7D44CF` | Feature highlights, categories |
| First Light | `#D45B90` | Decorative accents |
| Windy City | `#8A999E` | Neutral accents, muted text, borders |

### Tertiary Colors

| Name | Hex | Usage |
|------|-----|-------|
| Iceberg | `#003545` | Dark backgrounds, hero sections |
| Ruby Sky | `#3C0045` | Dark gradient accents |
| Violet Dawn | `#1C0045` | Deep background gradients |
| Winter | `#24323D` | Dark UI surfaces, footers |

## Bundled Assets

This plugin includes official Snowflake brand assets in the `skills/snowflake-brand/assets/` directory:

```
assets/
├── Snowflake_Template_2025.pptx.zip  # Official 2025 PowerPoint template
├── Snowflake-Graphics-Package.zip    # Dot backgrounds, decorative elements
│
├── logos/Snowflake Logo/
│   ├── Digital/
│   │   ├── SVG/    # Vector logos for web
│   │   ├── PNG/    # Raster logos @1x and @2x
│   │   ├── EPS/    # Vector for design tools
│   │   └── AI/     # Adobe Illustrator source files
│   └── Print/
│       ├── EPS/    # CMYK vectors for print
│       └── AI/     # CMYK Illustrator files
│
├── colors/
│   └── Sowflake-Brand-Colors/
│       ├── CC ase/     # Adobe .ase swatch files (RGB + CMYK)
│       └── Sketch/     # Sketch palette file
│
├── partner-guidelines/
│   └── Snowflake-Logo-Partner-Guidelines.pdf
│
└── ui-elements/
    └── Snowflake-UI-Elements.sketch
```

The full Snowflake Brand Book PDF is available at [snowflake.com/brand-guidelines](https://www.snowflake.com/brand-guidelines/) and was used as the source for this skill's text definitions.

Large binary files (PDFs, ZIPs, EPS, AI) are tracked with [Git LFS](https://git-lfs.github.com/). Make sure you have Git LFS installed before cloning:

```bash
brew install git-lfs
git lfs install
git clone https://github.com/obs-gh-chrismilton/snowflake-brand-skill.git
```

## Repository Structure

```
snowflake-brand-skill/
├── plugin.json                        # Plugin manifest
├── README.md                          # This file
└── skills/
    └── snowflake-brand/
        ├── SKILL.md                   # Skill definition (loaded by Claude Code)
        ├── assets/                    # Official brand assets (see above)
        └── references/
            └── detailed-specs.md      # Full specs including CMYK/PMS values
```

## Source

All brand assets and guidelines are sourced from the official [Snowflake Brand Guidelines](https://www.snowflake.com/brand-guidelines/) page. This skill packages them for use within Claude Code.

## Access

This is a public repository. Anyone can clone it and use it as a Claude Code plugin. If you have questions or want to contribute, open an issue or reach out to Chris Milton.

## License

The Snowflake brand assets included in this repository are the property of Snowflake Inc. and are subject to Snowflake's brand usage guidelines. This plugin packages them for internal and partner use within Claude Code. Do not redistribute the assets outside of authorized Snowflake brand usage.
