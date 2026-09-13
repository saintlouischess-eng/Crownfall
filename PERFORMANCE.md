# Crownfall 0.36.0 final rendering measurements

Final production runtime, including the painted ceiling. NVIDIA GeForce RTX 5080, driver 610.88, INNOCN E49M1R with Windows HDR enabled. One development computer; minimum hardware requirements are not established.

| Preset | Standard SDR | Standard HDR | Wide SDR | Wide HDR |
|---|---:|---:|---:|---:|
| Low | 67.4 FPS | 40.4 FPS | 66.0 FPS | 39.5 FPS |
| Medium | 66.4 FPS | 45.4 FPS | 64.1 FPS | 35.0 FPS |
| High | 51.2 FPS | 38.2 FPS | 50.1 FPS | 25.4 FPS |
| Ultra | 51.7 FPS | 38.6 FPS | 51.2 FPS | 25.4 FPS |

Each result combines three five-second samples after two seconds of settling, with different preset orders. The viewport and initial pixel-ratio reference are locked. The scene contains 32 animated starting pieces, the command camera, sunbeams and shadows, and 100% ambient light. Engine searches and audio are off. SDR measures application render cadence; HDR counts completed output submissions. These are not physical display scan-out measurements, combat minimums, or guarantees for other GPUs.

| Window | Preset | Actual 3D render size |
|---|---|---:|
| Standard | Low | 1170 Ã— 734 |
| Standard | Medium | 1353 Ã— 848 |
| Standard | High | 1353 Ã— 848 |
| Standard | Ultra | 1353 Ã— 848 |
| Wide | Low | 2899 Ã— 734 |
| Wide | Medium | 3478 Ã— 880 |
| Wide | High | 4383 Ã— 1109 |
| Wide | Ultra | 4383 Ã— 1109 |

The nominal windows are 1920 Ã— 1080 and 5120 Ã— 1400, including the interface. High and Ultra can share internal resolution under these DPI settings; Ultra increases shadow-map size.

