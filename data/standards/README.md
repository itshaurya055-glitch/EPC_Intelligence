# Standards Directory

Place your data centre specification PDFs here for pre-indexing into the RAG knowledge base.

## Required Files

| File | Standard | Description |
|------|----------|-------------|
| `tia_942b.pdf` | TIA-942-B | Telecommunications Infrastructure Standard for Data Centers |
| `uptime_tier_spec.pdf` | Uptime Institute | Tier Classification System (Tier I–IV) |
| `bicsi_002.pdf` | BICSI 002 | Data Center Design and Implementation Best Practices |
| `bis_is3043.pdf` | BIS IS 3043 | Code of Practice for Earthing (Indian Standard) |

## Notes

- These are copyrighted documents. You must obtain them through proper licensing channels.
- The ingestion pipeline will automatically extract text, tables, and OCR scanned pages.
- Files are chunked into 800-token segments with 100-token overlap and embedded using `all-MiniLM-L6-v2`.
- Once indexed, the standards are stored in ChromaDB under the `standards` collection.
- Re-indexing is idempotent — existing collections are checked before re-processing.
