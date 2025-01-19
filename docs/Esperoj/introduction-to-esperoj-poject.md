# Introduction to Esperoj Project

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
wget -U esperoj -SO /dev/null "https://x.0ms.dev/q70/https://web.archive.org/web/20250106230454im_/https://mirrors.dotsrc.org/kiwix/zim/ifixit/ifixit_en_all_2024-12.zim"
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
