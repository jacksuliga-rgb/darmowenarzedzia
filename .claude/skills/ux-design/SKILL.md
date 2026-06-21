---
name: ux-design
description: UX/UI design skill using Canva. Use when the user wants to create visual designs, mockups, banners, social media assets, presentations, or any graphic content. Leverages Canva MCP tools to generate, edit, and export designs.
---

# UX Design Skill (Canva-powered)

Create, iterate on, and export visual designs using the Canva MCP integration.

## Workflow

Make a todo list for all tasks in this workflow and work through them one by one.

### 1. Understand the Design Request

Before touching any tool, clarify:
- **Purpose**: What is this design for? (landing page mockup, banner, presentation, social post, icon set, etc.)
- **Brand context**: Is there an existing brand kit or colors/fonts to follow?
- **Dimensions / format**: Does the user specify a size? If not, pick the most common for the use case.
- **Content**: What text, images, or data should appear?

If anything is ambiguous, ask one focused question before proceeding.

### 2. Check for Existing Assets

Before creating from scratch, check what already exists:

```
Search designs: search for relevant existing designs
List brand kits: check for brand kits with colors/logos/fonts
Search brand templates: look for reusable templates
```

Use `search-designs`, `list-brand-kits`, and `search-brand-templates` tools.

### 3. Choose Creation Strategy

| Situation | Tool |
|-----------|------|
| No existing template, free-form request | `generate-design` or `generate-design-structured` |
| Existing brand template to populate | `create-design-from-brand-template` |
| Copy and adapt an existing design | `copy-design` |
| Merge multiple designs | `merge-designs` |
| Resize an existing design | `resize-design` |

### 4. Generate or Edit the Design

#### Creating a new design with AI (`generate-design-structured`)

Preferred when the request is well-defined. Pass structured content blocks:
- headline text
- body copy
- color palette hints
- style keywords (e.g. "minimal", "bold", "professional", "playful")

#### Starting an editing transaction (`start-editing-transaction`)

Use when you need precise control over elements:
1. `start-editing-transaction` — opens an edit session
2. `perform-editing-operations` — apply changes (text, colors, layout)
3. `commit-editing-transaction` — save changes
4. If something goes wrong: `cancel-editing-transaction`

**Always commit or cancel every transaction you start.**

### 5. Review the Result

After creation or edits:
- `get-design-thumbnail` — retrieve a preview image to show the user
- `get-design-content` — inspect elements if further edits are needed
- `get-design-pages` — check all pages for multi-page designs

Show the thumbnail to the user and ask: "Does this look right, or should I adjust anything?"

### 6. Iterate on Feedback

Common adjustments:
- **Text changes** → editing transaction → `perform-editing-operations`
- **Resize for another platform** → `resize-design`
- **Different style** → `generate-design-structured` with updated style keywords
- **Add a comment for the user to review** → `comment-on-design`

### 7. Export the Final Design

```
get-export-formats → choose format → export-design
```

Common formats:
- `PNG` / `JPG` — for web use, banners, social media
- `PDF` — for print or documents
- `SVG` — for scalable icons or illustrations
- `MP4` / `GIF` — for animated designs

Download the exported file and deliver it to the user.

### 8. Organize (Optional)

If the project warrants it:
- `create-folder` — create a project folder
- `move-item-to-folder` — keep designs organized

## Design Principles

- **Consistency**: Use the brand kit colors, fonts, and logo whenever one exists.
- **Hierarchy**: Make the most important element the largest/most prominent.
- **Whitespace**: Don't fill every pixel — breathing room improves readability.
- **Contrast**: Ensure text meets WCAG AA contrast ratios (4.5:1 for body text).
- **Alignment**: Align elements to a grid; avoid arbitrary positioning.
- **One focal point per page**: Guide the viewer's eye to a single CTA or headline.

## Educational / Polish Context Notes

This repository (`darmowenarzedzia`) contains free offline tools for Polish teachers and special educators. When designing for this project:
- **Audience**: Teachers, special educators, school counselors — professional but approachable tone.
- **Language**: Polish UI labels and copy.
- **Color palette**: Consider calming, trustworthy colors (blues, greens) over high-energy ones.
- **Accessibility**: Large readable text, high contrast — some users may have visual impairments.
- **Branding**: Stowarzyszenie 2piny, creator Jacek Suliga / Focusense® method.

## Wrap Up

In your final message, provide:
- A thumbnail or export link for the delivered design
- The Canva design ID (so the user can open it directly in Canva)
- A brief summary of design decisions made (colors, fonts, layout rationale)
- Next steps if further iteration is expected
