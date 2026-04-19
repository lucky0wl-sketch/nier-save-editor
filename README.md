# Nier Save Editor

Web-based editor for the SQLite save database used by the `lunar-tear` server project.

It is designed for browsing and editing player-state tables with extra quality-of-life features:

- live schema-driven table browsing
- user-scoped filtering
- inline ID annotations
- `nierrein`-style English lookup resolution for common game entities
- quick editing for save rows in the browser

## Features

- Reads the live SQLite schema directly from the target save DB
- Lists users with summary stats
- Lets you inspect and edit every table
- Filters `user_*` tables to the selected player
- Resolves many IDs into English labels for:
  - characters
  - costumes
  - weapons
  - companions
  - memoirs / parts
  - debris / thoughts
  - materials
  - consumables
  - important items
- Provides character dropdown selection for `character_id` fields

## Requirements

- Go 1.26+
- `sqlite3` available in your `PATH`
- Access to a `lunar-tear` server with dumped asset directory containing:
  - `assets/master_data`
  - `assets/revisions`

## Local Development

### Running the program

Using the live `lunar-tear` player DB:

go run . \
  --db ../lunar-tear/server/db/game.db \
  --addr :8081 \
  --master-data ../lunar-tear/server/assets/master_data

Then access the web ui at 192.168.0.184:8081



<img width="1693" height="999" alt="image" src="https://github.com/user-attachments/assets/deb4e8f2-056d-4f7f-9bd3-da2a62cd8e70" />

