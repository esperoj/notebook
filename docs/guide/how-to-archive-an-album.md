# How to Archive an album
## Rename command

### Rename (1) to (01)
```bash
rename -n 's/\((\d+)\)/sprintf("(%02d)", $1)/e' *
```

## Script to ingest

```bash
echo "Please enter file name:"
read filename
mkdir -p "ingest-${filename}"
mv "${filename}" "ingest-${filename}"
cp ~/data/ingest_album_template.toml "ingest-${filename}"
vim "ingest-${filename}/ingest_album_template.toml"
rclone copy "ingest-${filename}" tmp:"ingest-${filename}" -P
run-command.sh -h codeberg -c "rclone copy -v 'tmp:ingest-${filename}' './ingest-${filename}' && time esperoj ingest_album \
  --metadata-file='ingest-${filename}/ingest_album_template.toml' \
  'ingest-${filename}/$filename'"
```