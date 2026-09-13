# Crownfall — Battle Chess

**Windows x64 · 0.36.0 beta**

**A fast, modern dedicated GPU is needed for smooth animations.** Crownfall renders a detailed 3D hall, animated armies and cinematic combat. Lower quality settings help, but do not make this a lightweight chess GUI.

Crownfall is a local medieval 3D chess game for two people sharing a computer, a human against a computer, or two chess engines. It includes Squire, a lightweight opponent, plus animated troops, combat, horses and separate army memorials. The board stands at the center of the great hall, with twenty-one distinct stained-glass windows, including a unique circular rose at each end and four flush pavements of inlaid medieval ceramic ornament. Painted columns, foliate capitals, heraldic shields and eighty-two animated candles complete the room. The Triumph of the Two Crowns, an original Baroque-inspired allegorical mural, spans the vault inside a modeled gilt surround. This follows the requested palace-ceiling visual direction and is a fantasy addition to the medieval hall. Use **Camera → Painted ceiling · Look upward**, right-drag to explore, and choose **Command** to return to the board. Photo mode retains the upward view for screenshots. Separate memorial rows retain both complete armies, including individual horse carts and promoted cavalry, with clear aisles for the recovery teams. This is a playable project with further production work ahead, not a finished AAA release.

## Start playing

1. Extract the **complete Windows ZIP** into a writable folder. Keep `Crownfall.exe`, `web` and all package files together. Do not run inside the ZIP.
2. Open **Crownfall.exe → New battle**, choose each commander and a time control, then begin.
3. Click a piece and a highlighted destination. Dots mark quiet moves; rings mark captures. Choose a promotion when prompted.
4. **Space** pauses play or skips an animation. Both clocks stop during animations, funeral processions and deliberate pauses.
5. **Continue battle** reopens your current or saved game paused; **Resume battle** restarts play.

Windows x64, graphics support for WebView2's 3D renderer, a writable game folder and **Microsoft Edge WebView2 Runtime** are required. The package includes .NET. Playing with Squire needs no account, external engine, paid asset, music software or internet connection.

If WebView2 is missing, close Crownfall, get the **Evergreen Standalone Installer for x64** from [Microsoft's WebView2 page](https://developer.microsoft.com/en-us/microsoft-edge/webview2/), install it and reopen Crownfall. Hardware minimums have not been established. Existing graphics measurements are from an RTX 5080 and a limited set of displays, without a guaranteed frame rate on other computers.

## Explore the hall

Arrow keys slide left/right and move forward/backward. Page Up / Down raises or lowers the camera; hold Shift to travel faster. Camera → Travel speed ranges from 0.25× to 3× and saves your preference.

Enable **Camera → Free flight** to turn in place with right-drag, use W A S D for travel and E / Q for height. Forward movement follows your gaze in free flight; ordinary arrow travel stays level. Existing custom action bindings take priority over these letter keys. **Home** or **Camera → Command** restores the board. Scroll zooms; middle-drag or Shift + right-drag pans. Photo mode also offers free flight while actors remain frozen.

Camera keys leave typing fields, sliders, dialogs, the title menu and the 2D board alone. Releasing the keys or switching away from the window stops movement. Cinematic cameras take control during combat and then restore your view. Keyboard exploration stays within the hall floor, exterior walls and curved ceiling; it is an inspection camera, without collision against individual pieces or furnishings.

## Engines and books

**Engine arsenal → Add engine .exe** connects a Windows UCI engine. Enter launch arguments or a working directory if required; retain its network and support files. All five standard option types are discovered: check, spin, combo, string and button. Filter options, browse paths, restore defaults and **Save options**. Options apply to paused active sessions; launch changes need a new process. Button commands require an active session.

Choose an engine independently for either army in **New match**; one profile can play both colors through separate processes. **Settings → Council** selects a human player's advisor. **Ask the council** requests advice; **Play suggestion** plays it. Your clock continues while asking. Analysis is from White's perspective; an advertised **MultiPV** option requests ranked alternatives. **UCI log** shows recent protocol traffic.

For GUI books, open **Opening books → Add .bin / PGN**, then assign a book under the engine's **Opening repertoire** or override either computer side in **New match**, including Squire. Choose weighted, best-weight or uniform selection, maximum half-moves and minimum weight. **Moves here** previews legal candidates. Human turns remain manual; engines search when out of book.

Polyglot files must remain at their imported paths; reimport after moving or changing one. PGN books index main lines and combine transpositions by frequency. Their index lives in `data/books`, so the source PGN can move. Limits are 25 MB and 300,000 indexed positions; reduce import depth for large collections. Book moves count on the clock. A reported lookup failure falls back to engine search.

Engine-native books remain configurable. Disable **OwnBook** if you want only the GUI book. Crownfall supports Polyglot and PGN, not ChessBase `.ctg`; no commercial books are bundled. Pondering and Chess960 are unavailable and their advertised switches are locked off. WinBoard/XBoard engines are not supported.

## Time controls and results

| Control | Behavior |
|---|---|
| Fischer increment | Adds increment after each completed move |
| Sudden death | One allowance for the game |
| Simple / US delay | Delays charging time at the start of each move |
| Bronstein delay | Refunds elapsed time up to the delay after a move |
| Multi-stage tournament | Independent side quotas; 1–8 stages ending in sudden death |
| Fixed time per move | Fresh allowance for each completed turn |
| Fixed engine depth / nodes | UCI search limit; no human clock |
| Untimed | Unlimited human time; configured engine think time |
| Japanese byo-yomi | Main time followed by renewable periods |
| Canadian overtime | Main time followed by timed blocks of moves |

Presets and custom fields are in **New match**. Delay/overtime use bounded engine think times because UCI has no native fields for them. Squire has practical time/depth caps in Settings. Pausing retains time already spent on the turn.

Standard rules include castling, en passant and all four promotions. **Agree draw** supports threefold repetition and 50-move claims, including an intended legal next move. Fivefold repetition, the 75-move rule, stalemate and proven dead positions end automatically; checkmate takes precedence. Agreed draws in engine matches are operator adjudications. **Resign** applies to the human side to move. Complete dead-position proof for every arbitrary composed position is not implemented.

## Saves and updates

Autosaves update after moves and pauses, and about every ten seconds during play. **Save history** retains the latest battle and up to twelve earlier positions, with interrupted-write recovery. **Save / export** creates named `.crownfall` games with players, clocks, blood and memorials. Use named saves for separate games. PGN preserves portable moves and headers; FEN preserves a position. **Load game** accepts one game or position and opens it paused.

Blood accumulates through the match and survives saves. Turning it off hides it; a new match starts clean. Chronicle review restores the historical position. **Take back** removes one half-move and restores its stored clock, blood and memorials when available. Older saves can recover only marks still present in their history.

Save failures remain visible. **Quit** offers retry, export-and-quit, or a separately confirmed exit without the latest changes; earlier successful saves remain available. New matches and imports replace the board, so make a named save when you want to keep a battle.

Player data is in `data` beside the executable, including settings in `data/webview`. Back up or move the **entire data folder**. Engines and Polyglot files are referenced by path; preserve them separately. Format-version-2 saves require Crownfall 0.34.1 or later.

To update, close Crownfall, extract the new package elsewhere, and run **Install-Crownfall.cmd**. Choose your existing game folder; the helper verifies application files and preserves `data`. It can also install to a new per-user folder and add a Start menu shortcut. The portable copy remains usable. This offline helper is not an automatic updater or Windows uninstall service. The package is not code-signed.

Opening the same installation again returns to the existing game instead of competing for saves. An engine failure pauses play; Resume can start a fresh engine for the same game. Resumed searches respect time left in the turn. Native response timestamps keep delayed screen updates from causing a false loss on time; engines that actually miss their deadline still forfeit. Concurrent stop requests safely share engine termination.

## Camera and photographs

Right-drag to orbit, scroll toward a piece to zoom, and middle-drag or **Shift + right-drag** to pan. **Camera → Command** restores the full-board view. Other presets include overhead play and each army's memorial area. **Focus** expands the board while retaining clocks and pause controls.

Toggle **2D board** for a small playable board. Drag its title bar, resize from its handle, flip independently, or reset its layout. With a square focused, arrow keys navigate and Enter or Space selects.

**Photo mode** freezes combat, cloth and debris, with a forward step of 1/30 simulation second. Adjust lens, light and framing, hide controls, and export a 1920- or 3840-pixel-wide PNG. **Piece gallery** presents all six actual designs for either army with optional labels. Finish or skip a procession before opening the gallery. Exports are SDR images for sharing, even with live HDR.

## Light, music and HDR

**Hall light** adjusts ambient light and armor reflections from **0–500%** in Camera, Settings and Photo mode. Camera and Settings save your chosen brightness; Photo mode temporarily previews it and restores your saved level when closed. **Sunbeams** and **Hall ground shadows** are separate; disabling hall shadows retains piece shadows. **Living armies** and **Playful taunts** can be disabled independently. Blood, funeral processions, cinematic/full-window combat and animation speed are adjustable.

The soundtrack has **20 complete original orchestral tracks, about 61 minutes 50 seconds**. It shuffles full tracks without mid-track switches for captures, funerals or checkmate. **Music** and **Effects** are separate. M toggles music; Settings saves volume. Muting or minimizing rests playback and resumes the same recording. Playback starts after your first interaction. [CREDITS.md](CREDITS.md) records the music-production credits.

For HDR, enable Windows **Use HDR** on the game monitor, then choose **Settings → High dynamic range → HDR · 1,000 nits and beyond**. Calibrate peak brightness, paper white and exposure. The 400–4,000-nit targets are not measured monitor output or DisplayHDR certification; this is not HDR10+ metadata. Moving to an SDR monitor falls back to SDR while retaining your preference. HDR costs additional rendering time; reduce quality or use SDR if needed.

## Default controls

| Key | Action |
|---|---|
| Space | Pause/resume or skip animation |
| F / C / H | Flip 3D board / cycle camera / toggle Focus |
| M | Toggle music |
| P / I | Photo mode / Piece gallery |
| F11 | Fullscreen |
| Escape | Leave Photo mode, close a dialog, or pause and return to the title |

**Settings → Readability & controls** provides 80–150% interface size, remappable gameplay shortcuts and highlight colors. The **Field manual** and title-screen **Getting started** guide provide in-game help.

## Troubleshooting and limits

- **Dark pieces or slow rendering:** adjust Hall light, reduce quality or use SDR. No universal 60 FPS or minimum GPU is established.
- **Engine stops or cannot start:** check its executable, network files, directory and options. After correcting the problem, resume the battle. Consult UCI log.
- **Book missing or changed:** reimport, replace or disable it.
- **Save failure:** keep the game open, resolve the storage issue and retry, or export to another writable folder. Do not delete `data` to repair an update.
- **Display process stopped:** restart and use Continue or Save history. Restart to retry HDR after a graphics-device failure.
- **Support:** Settings → Diagnostics exports a local report without moves, engine paths or protocol logs. Nothing uploads automatically.

Online multiplayer, engine tournaments, Chess960, pondering and a full study editor remain future work. Procedural characters, staged recovery, contact envelopes and constrained cloth are not photoreal actors, full ragdolls, cloth self-collision or universal mesh collision. Crowded custom positions and broader hardware, driver, speaker and long-session testing still need review. The title background is promotional art; Photo mode and the gallery show playable models.

The candidate passed 45 desktop validation runs and the creator's gameplay test. Fresh-profile saving, normal quit, paused reopening and duplicate-launch protection passed. See [performance measurements](PERFORMANCE.md). Broader Windows and GPU testing remains outstanding.


## Credits and distribution

See [CREDITS.md](CREDITS.md). The original source project is not part of this distribution.
