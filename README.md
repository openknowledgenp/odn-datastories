# Open Data Nepal – Data Stories Repository

This repository stores **data stories** for [Open Data Nepal](https://opendatanepal.com), written in **MDX** and managed via **Decap CMS**.  
These stories power the **blog/data story section** of the Open Data Nepal website.

---

## 📂 Folder Structure

```
content/
└── posts/ # All stories in MDX format
├── glacier-melt.mdx
├── climate-finance.mdx
└── ...
images/
└── <post-slug>/ # Images for each post
├── cover.jpg
└── chart.png
```

---

## ✍ Editing Stories

### **Preferred Method – via Decap CMS**
- Go to **`/admin`** on the Open Data Nepal website.
- Log in with your credentials.
- Create, edit, or delete posts from the visual interface.
- Upload images directly in the editor; they will be placed in the correct folder.

---

### **Manual Edits in the Repository**
If you edit stories **directly in GitHub**:
- Update the `.mdx` file in `content/posts/`.
- Place any images in the matching `images/<post-slug>/` directory.
- **Note:** Manual changes may require a site rebuild/deploy to appear online.

---

## 🎨 Writing in MDX

All posts are in **MDX format**, so you can use standard Markdown plus **custom components** for charts, callouts, and data insights.

### Standard Markdown Supported
- Headings (`#`, `##`, `###`)
- Paragraphs, emphasis, bold, code
- Lists (ordered/unordered)
- Blockquotes
- Links
- Images

### Custom MDX Components
You can also use:
- `<InteractiveChart />` – dynamic charts with selectable metrics
- `<DataInsight />` – highlight key statistics
- `<Callout />` – emphasize important notes
- `<Card />`, `<Button />` – styled UI elements

#### InteractiveChart

Embed dynamic charts with selectable metrics.
```mdx
<InteractiveChart
  type="line"
  title="COVID-19 Cases Over Time"
  description="Monthly reported cases in Nepal"
  data={[
    { date: '2020-01', cases: 120, deaths: 2, recovered: 50 },
    { date: '2020-02', cases: 300, deaths: 5, recovered: 250 }
  ]}
/>

```
#### DataInsight

Highlight key metrics or statistics.

```mdx
<DataInsight
  title="Total Renewable Energy Capacity"
  value="2,345 MW"
  trend="up"
  description="Compared to last year, renewable capacity grew by 8%."
/>
```

#### Callout
Draw attention to important notes or warnings.
```mdx
<Callout type="info" title="Data Source">
  This chart uses data from ICIMOD's 2023 Glacier Status Report.
</Callout>
```
### 🛠 Frontmatter for Each Post

Each .mdx file must begin with:
```
---
title: "Glaciers on the Edge"
date: "2025-08-15"
author: "Open Data Nepal"
tags: ["climate", "glacier", "GLOF"]
cover_image: "/images/glaciers-on-the-edge/cover.jpg"
---
```

### 🖋 Example MDX Story Structure
```mdx
---
title: "Glaciers on the Edge"
date: "2025-08-15"
author: "Open Data Nepal"
tags: ["climate", "glacier", "GLOF"]
cover_image: "/images/glacier-cover.jpg"
---

# Glaciers on the Edge

Nepal’s glaciers are melting at an unprecedented rate...

<InteractiveChart
  type="line"
  title="Glacier Area Change (2000–2020)"
  description="Based on ICIMOD glacier monitoring data"
/>

<DataInsight
  title="Glacial Lake Expansion Rate"
  value="3.5% per year"
  trend="up"
  description="Driven by increasing meltwater volume."
/>

<Callout type="info">
  This finding aligns with recent IPCC AR6 projections for the Hindu Kush Himalaya region.
</Callout>

```
