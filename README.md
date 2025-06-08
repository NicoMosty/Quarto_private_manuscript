# Quarto Manuscript Project

This repository contains a Quarto manuscript project with interactive elements, data visualizations, and mathematical content.

## Project Structure

```
├── main.qmd                # Main manuscript document
├── notebooks/              # Jupyter notebooks with data analysis
│   └── notebook-data-example.ipynb
├── _quarto.yml             # Quarto configuration file
└── references.bib          # Bibliography file
```

## Features

This Quarto manuscript demonstrates:

- YAML frontmatter with author metadata and manuscript settings
- Interactive figures created with Python/Matplotlib
- Tables, images, and videos
- LaTeX math equations
- Mermaid diagrams
- Callouts and code annotations
- Content rearrangement with shortcodes
- Margin content

## Getting Started

1. Clone this repository
2. Install Quarto: [https://quarto.org/docs/get-started/](https://quarto.org/docs/get-started/)
3. Render the document:

```bash
quarto render main.qmd
```

## Publishing Securely

This project can be published to Quarto Pub with password protection using Staticrypt:

1. First, render your document to HTML:

```bash
quarto render
```

2. Install Staticrypt:

```bash
npm install -g staticrypt
```

3. Encrypt your HTML files:

```bash
staticrypt _manuscript/*.html -r -d _manuscript
```
   When prompted, enter your password. Note that passwords less than 14 characters will trigger a warning, but you can proceed with a shorter password if desired.

4. Publish the encrypted files to Quarto Pub:

```bash
quarto publish --no-render
```

   Follow the prompts to:
   - Select "Quarto Pub" as the provider
   - Choose your account
   - Enter a site name for your publication

5. Your encrypted site will be available at: `https://[username].quarto.pub/[site-name]`

## License

This project is licensed under CC BY-SA 4.0 as specified in the manuscript metadata.

