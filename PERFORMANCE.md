# Crownfall 0.36.0 performance results

## RTX 3070 Laptop GPU: user-reported 1440p results

On 13 September 2026, Crownfall's creator reported the following results on a second computer using an **NVIDIA GeForce RTX 3070 Laptop GPU**, with Windows display resolution set to **2560 x 1440 (1440p)**. This GPU model has **8 GB of dedicated GDDR6 video memory**, according to [NVIDIA's specifications](https://www.nvidia.com/en-us/geforce/laptops/30-series/).

| Graphics preset | Reported FPS |
|---|---:|
| Ultra | ~40 |
| High | ~46 |
| Medium | ~51 |

These are approximate user-reported FPS readings, not recorded benchmark averages. Low has not yet been reported. HDR mode, internal 3D render resolution, laptop GPU power limits and minimum FPS during combat were not recorded. These observations do not establish a minimum GPU or VRAM requirement and should not be treated as a direct comparison with the controlled RTX 5080 measurements below.

## Measured on the RTX 5080 development computer

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
| Standard | Low | 1170 x 734 |
| Standard | Medium | 1353 x 848 |
| Standard | High | 1353 x 848 |
| Standard | Ultra | 1353 x 848 |
| Wide | Low | 2899 x 734 |
| Wide | Medium | 3478 x 880 |
| Wide | High | 4383 x 1109 |
| Wide | Ultra | 4383 x 1109 |

The nominal windows are 1920 x 1080 and 5120 x 1400, including the interface. High and Ultra can share internal resolution under these DPI settings; Ultra increases shadow-map size.
