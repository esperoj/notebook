# Archive a Comic

## Download

```bash
time gallery-dl --cbz "https://mangadex.org/title/16fea29f-2511-47e0-bdc5-cf73e08c7143"
```

## Upload

Upload the first file on the web. Remember to add publisher and contributor metadata. Get the metadata from https://myanimelist.net/

```bash
set -euo pipefail
find . -iname "*.cbz" | while read file
do
  ia upload identifier "$file" --metadata="mediatype:texts" --retries 10 --delete
done
```

## Add to database

```bash
esperoj ingest_comic identifier
```