# Ingest a Song

## 1. Check Availability on Streaming Services

- Try music link services like [Odesli](https://odesli.co/) or [Songwhip](https://songwhip.com/).
- Search for the song on streaming platforms such as Amazon Music, Deezer, or Apple Music.
- Use Google to search for the song.
- For soundtracks, visit [Sitting on Clouds](https://www.sittingonclouds.net/).
- For game soundtracks, check [KHInsider](https://downloads.khinsider.com/).

## 2. Download the Song

- If the song is available on popular streaming services:
  - Use [Lucida](https://lucida.to/) or [Yams](https://yams.tf/) to download.
- If the song is on YouTube:
  - Use [ytmdl](https://ytmdl.deepjyoti30.dev/search) to download.
- For other websites (e.g., [Nhaccuatui](https://www.nhaccuatui.com/)):
  - Analyze the network log to find the download link.
- For soundtracks:
  - Follow [this guide](https://fmhy.net/audiopiracyguide#media-soundtracks).

## 3. Find Lyrics

- Use [MusicEnc](https://www.musicenc.com/) for general lyrics.
- For Chinese songs, try [Kugeci](https://www.kugeci.com/).

## 4. Add Metadata

- Prefer to use the native language if you can understand it.
- Find a high-quality cover to add.

## 5. Upload to a Folder

Upload to a temporary folder `pcloud:temporary/ingesting`.

```bash
rclone copy -Pv . pcloud:temporary/ingesting
```

## 6. Ingest

- Download the temporary folder and ingest it.

```bash
run-command.sh -h codeberg -c "
  start.sh koofr caddy
  mkdir -p /home/esperoj/audio
  cd /home/esperoj/audio
  rclone copy -Pv pcloud:temporary/ingesting .
  esperoj ingest .
  stop.sh koofr caddy"
```

- Delete the temporary files.

```bash
rclone delete -v . pcloud:temporary/ingesting
```

# Reference

- [Audio Piracy Guide](https://fmhy.net/audiopiracyguide)