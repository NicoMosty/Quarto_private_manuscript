# Quarto Manuscript Project

This repository contains a Quarto manuscript project with interactive elements, data visualizations, and mathematical content.

## Project Structure

This repository contains a Quarto manuscript project template with the following structure:

```
├── main.qmd                # Main manuscript document
├── notebooks/              # Jupyter notebooks with data analysis
│   └── notebook-data-example.ipynb
├── _quarto.yml             # Quarto configuration file
├── _publish.yml            # Publication configuration
└── references.bib          # Bibliography file
```

## Configuration Files

### _quarto.yml

This file configures the Quarto project settings:

- `project.type: manuscript` - Defines this as a manuscript-type project
- `manuscript.article` - Specifies the main document (main.qmd)
- `manuscript.notebooks` - Lists notebooks to include with their titles
- `manuscript.meca-bundle` - Defines the MECA bundle output filename

Multiple output formats are configured:
- `html` - Web format with interactive features (comments, hover citations)
- `pdf` - PDF output with LaTeX support
- `jats` - Journal Article Tag Suite format for journal submissions

The file also configures Python execution settings and bibliography information.

### _publish.yml

This file contains publication settings for Quarto Pub, which is Quarto's publishing platform. It includes:

- `source: project` - Indicates the entire project should be published
- `quarto-pub` - Contains publishing destination information

**Note:** When working with this template, you should replace the placeholder publishing ID and URL with your own Quarto Pub information when ready to publish.

## Usage

Edit `main.qmd` to write your manuscript content and add your analysis notebooks to the `notebooks/` directory. Configure the output formats in `_quarto.yml` based on your publication requirements.


## Features

This Quarto manuscript demonstrates:

- YAML frontmatter with author metadata and manuscript settings
- Interactive figures created with Python/Matplotlib
- Tables, images, and videos
- LaTeX math equations
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

