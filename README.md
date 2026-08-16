# Sunnify Colab Playlist Downloader

A Google Colab notebook that downloads Spotify playlists, albums, or tracks as local audio files (MP3 by default) with embedded artwork and tags. Built on top of [Sunnify](https://github.com/sunnypatell/sunnify-spotify-downloader), this notebook runs entirely in the cloud – no local installation required – and packages your downloaded music into a ZIP file that is saved directly to your computer.

> **Legal Disclaimer**  
> This project is for **educational and personal use only**. Download only content you own or have permission to download. Respect the laws of your jurisdiction. See [DISCLAIMER.md](DISCLAIMER.md) for full terms.

---

## Features

- Downloads **playlists, albums, or single tracks** from Spotify.
- Saves files in **MP3, M4A, Opus, FLAC, or WAV** (quality selectable).
- Embeds **metadata** (title, artist, album, year, track number) and **cover art** into each file.
- Runs entirely inside Google Colab – no local dependencies besides a browser.
- **Resumes automatically** if interrupted: re‑run the notebook and it will skip already downloaded tracks.
- Outputs a single ZIP file ready for download.

---

## Open in Colab

Click the badge below to open the notebook directly in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<your-username>/<your-repo>/blob/main/Spotify_Playlist_Downloader.ipynb)

> Replace `<your-username>` and `<your-repo>` with your actual GitHub details.

---

## How to Use

1. **Open the notebook in Colab** using the badge above (or upload the `.ipynb` file manually).
2. **Run each cell sequentially** (Runtime → Run all is recommended).
3. When prompted, **paste your Spotify playlist/album/track URL** in the designated cell (Cell 5).
4. (Optional) Adjust the audio **format and quality** by editing the command in Cell 6.
5. Let the notebook run – progress updates appear every few seconds without flooding the page.
6. Once finished, the notebook will:
   - Locate the output folder.
   - Compress all tracks into a ZIP file.
   - Trigger a browser download of the ZIP.
7. Unzip the downloaded file on your local machine to access your music.

---

## Customization

- **Audio Format**: In Cell 6, change `--format` to one of `mp3`, `m4a`, `opus`, `flac`, or `wav`.
- **Bitrate / Quality**: Use `--quality 128` (or `192`, `256`, `320`) for lossy formats. Lossless formats ignore this flag.
- **Output Folder**: The notebook saves files to `downloaded_playlist` inside Colab’s working directory. You can change this by editing the `--out` argument.

See the full CLI reference in the [Sunnify documentation](https://github.com/sunnypatell/sunnify-spotify-downloader/blob/main/docs/CLI.md).

---

## How It Works

1. Clones the Sunnify repository and installs its dependencies inside Colab.
2. Uses Sunnify’s command‑line interface to fetch track metadata from Spotify’s public pages (no account required).
3. Downloads matching audio via YouTube (using `yt-dlp`) and transcodes it locally with FFmpeg.
4. Writes metadata and cover art into each file using Mutagen.
5. Zips the final folder and triggers a download to your computer.

> **Note**: The pre‑compiled Sunnify binary may fail in Colab due to a GLIBC version mismatch. This notebook builds from source to avoid that issue.

---

## Runtime & Limits

- Colab provides a **free GPU/CPU runtime** with a 12‑hour maximum session.
- Downloading a large playlist (200+ tracks) can take **30–90 minutes**.
- If the runtime disconnects, simply re‑run the notebook from the top; already downloaded tracks are skipped automatically.

---

## Disclaimer

**This project is intended solely for educational purposes and personal backups of content you own.**  
Downloading copyrighted material without authorization may violate the laws of your country. The developer assumes no liability for misuse. Please support artists by purchasing their music or using authorized streaming services.

Full disclaimer: [DISCLAIMER.md](DISCLAIMER.md)

---

## Contributing

Contributions, issues, and feature requests are welcome.  
Feel free to fork the repository and submit pull requests.

---

## License

This notebook is distributed under the same custom educational license as Sunnify. See [LICENSE](LICENSE) for details.

---

**Author**: Sunny Jayendra Patel
