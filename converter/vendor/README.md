# Vendor Libraries

This directory contains libraries for local-only file conversion tools that work offline.

## Included Libraries

### PDF-lib 
- **Path**: `pdf-lib/`
- **Files**:
  - `pdf-lib.min.js` - PDF generation and manipulation library
- **Purpose**: PDF file creation, merging, image to PDF conversion
- **Version**: 1.17.1

### PDF.js
- **Path**: `pdfjs/`
- **Files**:
  - `pdf.min.js` - PDF rendering library
  - `pdf.worker.min.js` - PDF rendering web worker
- **Purpose**: Render PDF files to canvas for preview generation
- **Version**: 3.11.174

## Library Roles

- **PDF-lib**: PDF creation, manipulation, saving (write)
- **PDF.js**: PDF rendering, preview (read)

The combination of these two libraries provides a complete PDF processing environment.

## Features

- **Complete Local Operation**: All functions available without network connection
- **Privacy Protection**: Files are not transmitted to external servers
- **Fast Loading**: Instant library loading without CDN dependencies
- **Optimized Performance**: Prevents duplicate parsing through caching

## Update Method

To update libraries:

```bash
# Update PDF-lib  
curl -o pdf-lib/pdf-lib.min.js https://cdn.jsdelivr.net/npm/pdf-lib@latest/dist/pdf-lib.min.js

# Update PDF.js
cd pdfjs/
curl -L https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.min.js -o pdf.min.js
curl -L https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.worker.min.js -o pdf.worker.min.js
```

## Library Usage

```javascript
// Initialize PDF.js
pdfjsLib.workerSrc = '../vendor/pdfjs/pdf.worker.min.js';

// PDF rendering (preview)
const pdf = await pdfjsLib.getDocument(buffer).promise;
const page = await pdf.getPage(1);

// PDF creation/manipulation (save)
const doc = await PDFLib.PDFDocument.create();
const page = doc.addPage();
```