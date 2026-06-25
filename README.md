# Dub Chunk Completer

Dedicated pipeline to finish the FAILED chunks left silent by the main
Dubz-Final dubbing pipeline.

## Flow
1. Main pipeline uploads failed raw chunks to Drive: `Dubz/Chunks`
2. Here: press Actions -> "Complete Failed Chunks" -> Run.
3. Each chunk gets its OWN matrix job (up to 256, 20 parallel) and is dubbed.
4. Dubbed chunk -> `Dubz/ChunksDone`. Raw original -> `Dubz/Chunks/archive`.
5. A chunk that still fails is left in `Dubz/Chunks` for the next run.

## Secrets
- RCLONE_CONF (required) - rclone Google Drive config text
- DUB_BASE_URL (optional)

Manual only, no cron.