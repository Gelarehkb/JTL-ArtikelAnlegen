# JTL-ArtikelAnlegen

An AI-assisted tool for creating and enriching clothing/apparel product master data for [JTL](https://www.jtl-software.com/). It combines a spreadsheet-style editor with AI-powered classification, translation, and text-generation features to speed up building JTL-ready Artikelstammdaten.

## Features

- **Spreadsheet editor** — enter and edit product rows (name, code, color, size, EAN, HAN, prices, quantity) with paste, undo, find & replace, and CSV/dictionary import
- **Artikel anlegen** — groups variants by name/code/color and builds JTL-compatible article rows (Artikelnummer, VaterArtikel, pricing, delivery/replenishment settings), including an EK < VK sanity check
- **AI classification & naming** — Supabase edge functions (`classify-products`, `restructure-names`, `translate-article-names`) use an LLM to classify products, restructure article names, and translate article names
- **AI text generation** — in-app calls to the Gemini API for generating and refining product text
- **Multi-language support** with translation dictionaries for categories, colors, and sizes

## Tech Stack

- React + TypeScript, built with Vite
- shadcn-ui components on top of Tailwind CSS
- [Supabase](https://supabase.com/) edge functions for backend/AI processing
- Google Gemini API for AI text generation
- Docker setup included for containerized deployment

## Getting Started

```bash
# install dependencies
npm i

# copy environment variables and fill in the required values (e.g. VITE_GEMINI_API_KEY)
cp .env.example .env

# start the dev server
npm run dev
```

### Supabase functions

The `supabase/functions` directory contains the edge functions used for AI classification, name restructuring, and translation. See `supabase/config.toml` for configuration.

### Docker

A Docker setup is included for running the app in a container; see the project files for details.

## Project Origin

This project was originally scaffolded with [Lovable](https://lovable.dev/) and has since been extended with custom pages and AI-powered backend functions.

## License

No license specified yet.
