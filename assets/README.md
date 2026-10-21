# Asset preparation

- 11 full-frame JPEG image copies (1109 × 2400), 11 JPEG thumbnails (296 × 640), 4 JPEG video posters, 4 MP4 videos. No image crops.
- MP4s contain video only: each verified by ffprobe to have exactly one H.264 video stream and zero audio streams. All four fully decoded successfully with FFmpeg. No inert original audio payload was retained by the remux/transcode process.
- Camera original was HEVC; converted to H.264/yuv420p, 720 × 1280, 8.30 s. Other videos remuxed without video re-encoding: 22.989633 s, 9.933333 s, 12.243333 s (see exact metadata).
- MP4 faststart enabled. No uploads, no publish, and no original files modified. Source hashes recorded in verification.json.
- JPEGs resized with Windows System.Drawing high-quality bicubic interpolation and JPEG quality 88 (detail) / 82 (thumb).
- FFmpeg/ffprobe 9.0.2 essentials Windows build downloaded from https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip and kept only under session tmp, outside deployable website.
- JPEG and FFmpeg decoding validation is local. Browser playback was not separately tested by this asset task; parent can test final website integration.
- Parent UI should use object-fit: contain for image/video detail and set muted/defaultMuted on video elements as an additional safeguard.
