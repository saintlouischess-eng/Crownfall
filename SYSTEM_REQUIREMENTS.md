# Hardware and performance

## Startup repair — packaging revision 2

The first public download omitted `WebView2Loader.dll`, a required Microsoft component. This revision includes the signed x64 DLL and an updated installation manifest. The game executable and gameplay assets are unchanged.

If you already downloaded the original 0.36.0 beta, use [the small startup repair](https://github.com/saintlouischess-eng/Crownfall/releases/download/v0.36.0-beta.2/Crownfall-0.36.0-Startup-Repair.zip). Close Crownfall and extract the repair into the folder containing `Crownfall.exe`, allowing its installation manifest to be replaced. Saved games and settings are preserved. Then run `Crownfall.exe` again.

Microsoft Edge WebView2 Runtime is still required. Installing that Runtime alone does not replace Crownfall's missing loader DLL.

**A fast, modern dedicated GPU is needed for smooth animations.** Crownfall renders a detailed 3D hall, animated armies and cinematic combat. Lower quality settings help, but do not make this a lightweight chess GUI.

- Windows x64 and a writable installation folder.
- A fast, modern dedicated graphics card with current drivers and hardware-accelerated WebView2 3D rendering.
- Microsoft Edge WebView2 Runtime. The .NET runtime is included with the game.
- An HDR-capable monitor with Windows HDR enabled if you want HDR output. SDR is supported.
- Enough free storage for both the downloaded ZIP and the extracted game.

This beta was tested on an NVIDIA GeForce RTX 5080. No minimum GPU model has been established. Integrated graphics, older GPUs and other hardware have not been qualified. Do not assume every modern GPU will deliver smooth play.

For smoother animation, start with **Low or Medium quality in SDR**. A smaller window can help. HDR, ultrawide output and higher shadow quality cost additional rendering time. Keep engine thread and hash settings within your computer's available resources.

## Measured on the development computer

| Preset | Standard SDR | Standard HDR | Ultrawide SDR | Ultrawide HDR |
|---|---:|---:|---:|---:|
| Low | 67.4 FPS | 40.4 FPS | 66.0 FPS | 39.5 FPS |
| Medium | 66.4 FPS | 45.4 FPS | 64.1 FPS | 35.0 FPS |
| High | 51.2 FPS | 38.2 FPS | 50.1 FPS | 25.4 FPS |
| Ultra | 51.7 FPS | 38.6 FPS | 51.2 FPS | 25.4 FPS |

RTX 5080, driver 610.88, INNOCN E49M1R. Nominal windows: 1920 x 1080 and 5120 x 1400, including the interface. Internal rendering resolution varies with preset and DPI. Three five-second samples per setting, 32 animated starting pieces, engine searches and audio off. These are application rendering/output measurements, not combat minimums or guaranteed frame rates. Full details: [Performance measurements](PERFORMANCE.md).

If WebView2 is missing, install Microsoft's [Evergreen Standalone x64 Runtime](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) and reopen Crownfall. The application is unsigned; this beta does not claim Microsoft certification.
