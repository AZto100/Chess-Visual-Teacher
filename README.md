Run from Github : https://azto100.github.io/Chess-Visual-Teacher/

# Chess Teacher

All downloaded files then remain local; the app uses no external runtime service.

## Windows 10

1. Extract the ZIP fully.
2. Open its chess_teacher_setup folder.
3. Double-click Install-Windows.cmd. It invokes the included PowerShell downloader,
   with an execution-policy override only for that PowerShell process. It does not
   change your permanent PowerShell execution policy or install anything globally.
4. Open PowerShell in this folder, which contains index.html.
5. With Python 3 already installed, run:

   py -3 -m http.server 8765 --bind 127.0.0.1

6. Open http://127.0.0.1:8765 in your browser. Keep the terminal open.
   Ctrl+C stops the server. Do not open index.html directly with a file:// URL.


## WSL / Ubuntu

In the extracted folder, with curl and Python 3 installed:

   bash download-dependencies.sh
   python3 -m http.server 8765 --bind 127.0.0.1

Open http://127.0.0.1:8765 in the Windows browser (WSL localhost forwarding
must be available), or in a browser running inside the same Linux environment.

## The three runtime dependency files

vendor/chess.js
  https://cdn.jsdelivr.net/npm/chess.js@1.4.0/dist/esm/chess.js

engine/stockfish-19-lite-single.js
  https://github.com/nmrugg/stockfish.js/releases/download/v19.0.1/stockfish-19-lite-single.js

engine/stockfish-19-lite-single.wasm
  https://github.com/nmrugg/stockfish.js/releases/download/v19.0.1/stockfish-19-lite-single.wasm

These versions are pinned. The two Stockfish files must come from the same
release and keep their original names, in the same folder. A native Stockfish
Windows .exe is not a substitute for the browser JavaScript/WASM files.
The lite single-threaded build does not require cross-origin isolation headers.
No Node.js, npm, compilation or online chess account is needed for this setup.

## Sources and licensing

chess.js 1.4.0: BSD-2-Clause.
https://github.com/jhlywa/chess.js/tree/v1.4.0
https://jhlywa.github.io/chess.js/

Stockfish.js 19.0.1 engine: GPL v3.
https://github.com/nmrugg/stockfish.js/releases/tag/v19.0.1
https://github.com/nmrugg/stockfish.js/tree/v19.0.1
https://raw.githubusercontent.com/nmrugg/stockfish.js/v19.0.1/README.md
