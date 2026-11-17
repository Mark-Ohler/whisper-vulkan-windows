# whisper.cpp mit Vulkan für Windows

Fertig gebautes [whisper.cpp](https://github.com/ggml-org/whisper.cpp) mit **Vulkan**, damit Whisper unter Windows auch auf **AMD- und Intel-Grafik** läuft. Das offizielle Projekt liefert für Windows nur Builds für CPU und NVIDIA (CUDA).

- Quellcode: unverändert von `ggml-org/whisper.cpp`, Version siehe Release-Name.
- Gebaut ausschließlich von GitHub Actions, siehe [.github/workflows/build.yml](.github/workflows/build.yml). Jeder Build ist im Reiter "Actions" nachvollziehbar.
- Jedes Release enthält `whisper-cli.exe`, das Sprachbeispiel `jfk.wav`, die Lizenz und eine SHA-256-Prüfsumme.

## Benutzung

```
whisper-cli.exe -m ggml-large-v3-turbo.bin -f audio.wav -l auto -ojf
```

Modelle gibt es bei [Hugging Face](https://huggingface.co/ggerganov/whisper.cpp). Mit `-dev N` wählt man das Grafikgerät, die Liste steht beim Start in der Ausgabe (`ggml_vulkan: 0 = ...`).

Voraussetzung ist ein aktueller Grafiktreiber mit Vulkan-Unterstützung. Das ist bei AMD- und Intel-Treibern der Fall.

## Lizenz

whisper.cpp steht unter der MIT-Lizenz (`LICENSE-whisper.cpp.txt` im Paket). Der Build-Ablauf in diesem Repo steht ebenfalls unter MIT, siehe [LICENSE](LICENSE).
