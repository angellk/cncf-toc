---
name: marp-presentation
description: Create slide deck presentations from markdown using Marp. Use when you need to generate HTML/PDF presentations with consistent branding for TOC meetings, TAG updates, or project reviews.
license: Apache-2.0
compatibility:
  - Marp CLI
  - VS Code Marp extension
metadata:
  author: CNCF TOC
  version: 1.0.0
  type: skill
  tags:
    - presentation
    - documentation
    - markdown
    - slides
  validated-by: CNCF TOC (TOC meeting presentations)
  platform:
    marp:
      entrypoint: npx @marp-team/marp-cli
      config: .marprc.yml
---

# Marp Presentation Skill

Create professional slide deck presentations from markdown using Marp with CNCF branding.

## When to Use

- TOC meeting presentations
- TAG liaison updates
- Project due diligence presentations
- Annual report presentations
- Community updates

## Prerequisites

```bash
# Install Marp CLI
npm install -g @marp-team/marp-cli

# Or use npx (no install needed)
npx @marp-team/marp-cli --version
```

## Creating a Presentation

### 1. Create Markdown File

Create a markdown file with Marp frontmatter:

```markdown
---
marp: true
theme: cncf
paginate: true
---

# Your Presentation Title

Your Name
Date

---

## Slide 2

- Point 1
- Point 2
- Point 3
```

### 2. Generate HTML Presentation

```bash
# Using themes from this skill
marp --theme-set themes/cncf.css your-presentation.md -o output.html

# Watch mode for live preview
marp --theme-set themes/cncf.css your-presentation.md -o output.html --watch
```

### 3. Generate PDF

```bash
marp --theme-set themes/cncf.css your-presentation.md -o output.pdf --allow-local-files
```

## Available Themes

### CNCF Theme (Default)

Official CNCF brand colors and styling for TOC/TAG presentations.

**Features:**
- CNCF blue primary color (#436B95)
- Kubernetes blue accent (#326CE5)
- Clean typography
- Proper spacing and hierarchy
- Footer with CNCF logo placeholder

**Usage:**
```markdown
---
marp: true
theme: cncf
---
```

### Customization

Override theme variables in your markdown frontmatter:

```markdown
---
marp: true
theme: cncf
style: |
  section {
    background-color: #f0f0f0;
  }
  h1 {
    color: #326CE5;
  }
---
```

## Presentation Patterns

### Title Slide

```markdown
---
marp: true
theme: cncf
paginate: false
class: title
---

# Project Name Incubation Review

**Presenter:** Your Name
**Date:** YYYY-MM-DD
**Meeting:** TOC Meeting

---
```

### Content Slide

```markdown
## Section Title

Content goes here

- Bullet point 1
- Bullet point 2
```

### Two-Column Layout

```markdown
<div class="columns">
<div>

### Left Column

- Point 1
- Point 2

</div>
<div>

### Right Column

- Point A
- Point B

</div>
</div>
```

### Image Slide

```markdown
## Architecture Diagram

![Architecture](images/architecture.png)
```

## Advanced Layouts

### Compact Section (Dense Content)

```markdown
<!-- _class: compact -->

## Dense Information

- More content per slide
- Smaller font size (20px)
- Tighter spacing
```

### Readout Section (Status Reports)

```markdown
<!-- _class: readout -->

## Project Status

### Highlights
- Achievement 1
- Achievement 2

### Issues
- Issue 1
- Issue 2
```

### Grid Layouts

**2-Column Grid:**
```markdown
<div class="grid-2col">
<div class="section-positive">

### Strengths
- Point 1
- Point 2

</div>
<div class="section-negative">

### Weaknesses
- Issue 1
- Issue 2

</div>
</div>
```

**3-Column Grid:**
```markdown
<div class="grid-3col">
<div>Column 1</div>
<div>Column 2</div>
<div>Column 3</div>
</div>
```

### Colored Section Headers

```markdown
<div class="section-positive">

### Highlights
- Good thing 1
- Good thing 2

</div>

<div class="section-negative">

### Issues
- Problem 1
- Problem 2

</div>

<div class="section-recommendations">

### Recommendations
- Action 1
- Action 2

</div>
```

## Configuration

Create `.marprc.yml` in your repository root:

```yaml
# Marp CLI configuration
engine:
  convert:
    allowLocalFiles: true
```

## Best Practices

1. **One idea per slide** - Keep slides focused
2. **Use bullet points** - Not paragraphs
3. **Include visuals** - Diagrams over text
4. **Consistent branding** - Use CNCF theme
5. **Accessible colors** - High contrast ratios
6. **Readable fonts** - Minimum 24pt body text

## Troubleshooting

**Problem:** Theme not found

```bash
# Make sure to specify theme path
marp --theme-set /path/to/themes/cncf.css presentation.md
```

**Problem:** Images not loading in PDF

```bash
# Add --allow-local-files flag
marp --allow-local-files presentation.md -o output.pdf
```

**Problem:** Custom fonts not rendering

```bash
# Install fonts system-wide or use web fonts
# CNCF uses Inter font (https://fonts.google.com/specimen/Inter)
```

## Examples

See `references/example-toc-presentation.md` for a complete example.

## Resources

- [Marp Documentation](https://marpit.marp.app/)
- [CNCF Brand Guidelines](https://github.com/cncf/artwork/blob/master/other/cncf-brand-guidelines.pdf)
- [CNCF Artwork Repository](https://github.com/cncf/artwork)
