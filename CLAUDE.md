# Pandora's AI Box

A personal AI learnings hub. HTML files documenting what I've learned about AI and what I still want to learn — a reference to reflect on and refresh, replacing PowerPoint notes.

## Structure

```
index.html          ← home page (Learned + To Learn card grids)
style.css           ← shared dark theme, do not modify the design
pages/
  template.html     ← copy this for every new topic page
  *.html            ← one file per topic
```

## Adding a new topic

### 1. Create the page
Copy `pages/template.html` and name it after the topic, lowercase with hyphens:
```
pages/rag.html
pages/fine-tuning-vs-prompting.html
pages/ai-agents.html
```
Fill in the title, subtitle, category tag, and content sections.

### 2. Add a card to index.html
Find the right section (`Learned` or `To Learn`) and add a card.

**Learned card** (links to the page):
```html
<a class="card" href="pages/your-topic.html">
  <div class="card-title">Topic Title</div>
  <div class="card-desc">One or two sentences describing what this covers.</div>
  <div class="card-meta">
    <span class="tag">CATEGORY</span>
    <span class="tag status-learned">Learned</span>
  </div>
</a>
```

**To Learn card** (no link yet, just a placeholder):
```html
<div class="card">
  <div class="card-title">Topic Title</div>
  <div class="card-desc">One or two sentences describing what this covers.</div>
  <div class="card-meta">
    <span class="tag">CATEGORY</span>
    <span class="tag status-to-learn">To Learn</span>
  </div>
</div>
```

When a To Learn topic gets a page written, change `<div class="card">` to `<a class="card" href="...">`, close with `</a>`, and change `status-to-learn` to `status-learned`.

## Category tags

Use one of these (or add a new one if it doesn't fit):

| Tag | Use for |
|-----|---------|
| `Fundamentals` | Core concepts — what AI is, how LLMs work, key terminology |
| `Architecture` | How AI systems are built — RAG, embeddings, vector DBs, fine-tuning |
| `Agents` | Autonomous AI, tool use, multi-agent systems |
| `Prompting` | Prompt engineering, techniques, patterns |
| `Strategy` | When and how to introduce AI, business decisions |
| `Tools` | Specific products, APIs, platforms |
| `Use Cases` | Real-world applications and examples |

## Page template sections

The template has these sections — keep them all, leave blank if not yet filled:

- **The one-sentence version** — the simplest possible summary
- **Key concepts** — named subsections with `<h3>` for each concept
- **How to think about it** — mental model or analogy that made it click
- **Key insight callout** — the thing worth highlighting up front
- **Practical applications** — bullet list of real uses
- **Watch out for callout** — gotchas, limits, misconceptions (use the `.watch-list` style for multiple pitfalls)

Do not add a "My takeaways" or personal-notes section. Reflections belong inline with the content, not in a separate placeholder.

## Callout types

```html
<div class="callout tip">      ← green left border, for insights
<div class="callout warning">  ← orange left border, for gotchas
<div class="callout">          ← purple left border, neutral
```

For multiple pitfalls inside a `.callout.warning`, use `<ul class="watch-list">` with each `<li>` starting with a bold lead-in:

```html
<div class="callout warning">
  <strong>Watch out for</strong>
  <ul class="watch-list">
    <li><strong>Lead-in.</strong> Explanation.</li>
    <li><strong>Lead-in.</strong> Explanation.</li>
  </ul>
</div>
```
