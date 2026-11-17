# Grandmaster AI — Android port (starter build)

This is a standalone Android WebView app adapted from the uploaded Grandmaster AI / Chess Assistant Pro v3.0.0 source. Original author and license notices are retained; see `LICENSE`.

## What is implemented in this Android port
- Native Android launcher activity with an embedded, touch-friendly analysis interface.
- Chessboard rendered from a full FEN position.
- Board flip control.
- Best-move arrow with source and destination square highlights.
- Engine selector: Auto-Hybrid, Stockfish Online, Lichess Cloud, Syzygy Tablebase.
- The same three remote analysis services/endpoints described in the original source.
- Original `openings.js` database and its opening-identification function.
- Basic API request/success/average-latency counters.
- No auto-play, move dispatch, mouse automation, humanization, jitter, stealth, panic mode, or Chess.com/Lichess page overlay.

## Important limitations (not yet implemented)
- The original extension detects FEN by reading Chess.com/Lichess page DOM. A standalone Android app cannot reuse those selectors; this port instead accepts a FEN pasted into the app.
- No legal-move board editor, PGN importer, local/offline Stockfish binary, full original telemetry log/pagination, audio chimes, or original extension tabs yet.
- Stockfish is the remote Stockfish Online API, not a bundled offline engine.
- Cloud features require internet and third-party endpoints may be unavailable, rate-limited, or change their API.
- Opening recognition uses the exact supplied original opening database, which identifies positions by piece placement; it is not a full move-history PGN opening classifier.
- This app is for study and post-game analysis, not assistance during live rated games.

## Build APK using GitHub from an Android phone
1. Extract this ZIP.
2. Create a new GitHub repository.
3. Upload the **contents** of this folder to the repository root (not the ZIP file and not an extra parent folder).
4. Open **Actions** and run **Build Android APK**.
5. Download the `GrandmasterAI-debug-apk` artifact from the completed workflow run.
6. Extract it and install `app-debug.apk` on Android. Allow installation from the browser/files app if Android asks.

The workflow builds a debug APK. It is not a Play Store release-signed APK. The build has not been verified on a physical Android device in this environment.
