---
title: Embed Showcase
tags: demo, embeds, media, guide
---
# Embed Showcase

## In Exports

All embedded media is encoded directly into HTML exports, making the output fully portable — share a single `.html` file with audio, video, PDFs, and images included. PDF and DOCX exports render the content inline as well.

cyberWriter supports embedding multiple file types inline using the `![[filename]]` vault syntax. This document demonstrates each type.

---

## Data Embeds

### CSV Table
CSV files render as styled HTML tables:

![[embeds/sample_csv.csv]]

### TSV Table
Tab-separated files work the same way:

![[embeds/sample_tsv.tsv]]

---

## Media Embeds

### Audio
Record a voice note with the mic button, or embed any audio file:

`![[audio/Voice Note 2026-04-13 at 19.54.00.m4a]]`

> [!note]  A Note from JT
> ![[audio/note_from_JT.mp3]]


> [!tip] Try it
> Click the **mic button** in the editor toolbar to record a voice note. It saves to the `audio/` folder and inserts the embed automatically.

### Video
Embed video files up to 50MB inline (larger files show a placeholder):

`![[your-video.mp4]]`

![[CyberWriterTeaser.mp4]]


> [!note] Supported formats
> mp4, mov, m4v, webm

[pagebreak]

### Images
The classic embed — images render inline:

![[nexus-patch.png]]

> [!info] Image formats
> png, jpg, jpeg, gif, webp, svg, bmp, heic

---

## Document Embeds

### PDF
PDF files render as scrollable inline viewers:

`![[your-document.pdf]]`

> [!tip] Try it
> Drop a `.pdf` file into your vault and embed it with `![[filename.pdf]]`
![[embeds/Embed Showcase.pdf]]

---

## YouTube

Paste a YouTube link and it renders as a clickable card that opens in your browser:

[Rick Astley - Never Gonna Give You Up](https://www.youtube.com/watch?v=dQw4w9WgXcQ)

---

## Drag & Drop

You can also drag files from the vault sidebar directly into the editor:
- **Markdown files** insert as `[[wikilink]]`
- **Everything else** inserts as `![[embed]]` with the full path

Right-click any file in the sidebar → **Copy Wikilink** uses the same syntax.

---

## Text Embeds

### Markdown Note
Embed any `.md` file — it renders with full formatting:

![[embeds/readme.md]]

### Plain Text
Text files render with an accent border:

![[embeds/notes.txt]]

### RTF
Embed RTF Files right into the doc

![[embeds/Why_cyberWriter.rtf]]


---
