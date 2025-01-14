# Introduction to Esperoj Project

## File Locations

| Audio, Document, Picture | Game, Comic, Video, Software | Workspace | Backup      |
|--------------------------|------------------------------|-----------|-------------|
| Archive.org              | Archive.org                  | Filen     | Archive.org |
| Catbox.moe               | Catbox.moe                   | Pcloud    | Backblaze   |
| FileDitch                | FileDitch                    | Phone     | Filen       |
| Filen                    | Lain.la                      |           | Pcloud      |
| Lain.la                  |                              |           | Phone       |
| Pcloud                   |                              |           |             |


- public files, and cache store in Backblaze.
- Temporary files store in Pcloud.
- Archive files store in Filen and Pcloud.
- pcloud-0: workspace, backup, documents, picture, and temporary files
- pcloud-1: music, archive, 

Here is the config for esperoj

```bash
echo $(echo '
  "workspace-0=pcloud-0:esperoj/workspace" "workspace-1=mega:esperoj/workspace"
  "backup-0=pcloud-0:esperoj/backup" "backup-1=megadisk:esperoj/backup"
  "audio-0=pcloud-1:esperoj/audio" "audio-1=mega:esperoj/audio"
  "document-0=pcloud-0:esperoj/document" "document=mega:esperoj/document"
  "picture-0=pcloud-0:esperoj/picture" "picture-1=mega:esperoj/picture"
  "archive-0=pcloud-1:esperoj/archive" "archive-1=mega:esperoj/archive"
  "cache=b2:esperoj-cache"
  "public=b2:esperoj-public"
  "tmp=pcloud-0:esperoj/tmp"
')
```

## File Ingestion

1. Ingest files.
2. Add metadata to the database.

## Checksum Verification Schedule

1. Select a subset of files.
2. Verify all selected files.

## Replication

1. Sunc workspace from phone to workspace-0 to workspace-1.
2. Sync backup-0 to backup-1.
3. Create a backup file from backup-0, and upload it to [public](https://public.esperoj.eu.org), and then archive using Archive.org every Sunday night and Wednesday.
4. Use Archive.org to save esperoj website for reference.

## Maintenance

- Upgrade python version when Vercel and Nuitka support it.
## Issues

### Speedtest

#### Archive.org
```bash
wget -U esperoj -SO /dev/null "https://x.0ms.dev/q70/https://web.archive.org/web/20240904034409if_/https://x.0ms.dev/q70/https://fsn1-speed.hetzner.com/1GB.bin"
```

#### Fielditch
```bash
wget -U "firefox" -SO /dev/null "https://big.fileditchstuff.me/b49/whTIpzGvVaSJZXkfTrFk.zip"
```

#### Catbox.moe
```bash
wget -U "firefox" -SO /dev/null "https://x.0ms.dev/q70/https://files.catbox.moe/g8ow4s.mp4?s=$RANDOM"
```

### Files exist in multiple formats, such as converting from EPUB to PDF and PDF/A.
