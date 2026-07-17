# Third-Party Licenses

N-Labeler 本体は MIT ライセンスです（[LICENSE](LICENSE) を参照）。
配布ビルド（`N-Labeler.exe` の同梱物）には以下のサードパーティ製ソフトウェアが
含まれます。各ライセンス全文は [`licenses/`](licenses/) フォルダに同梱しています。

| コンポーネント | バージョン | ライセンス | ライセンス全文 |
|---|---|---|---|
| Qt for Python (PySide6, shiboken6) | 6.11.1 | LGPL-3.0 | [Qt-PySide6-LGPL-NOTICE.txt](licenses/Qt-PySide6-LGPL-NOTICE.txt) |
| pyqtgraph | 0.14.0 | MIT | [pyqtgraph-LICENSE.txt](licenses/pyqtgraph-LICENSE.txt) |
| NumPy | 2.4.6 | BSD-3-Clause | [numpy-LICENSE.txt](licenses/numpy-LICENSE.txt) |
| SciPy | 1.17.1 | BSD-3-Clause | [scipy-LICENSE.txt](licenses/scipy-LICENSE.txt) |
| python-soundfile | 0.14.0 | BSD-3-Clause | [python-soundfile-LICENSE.txt](licenses/python-soundfile-LICENSE.txt) |
| libsndfile (soundfileが同梱) | — | LGPL-2.1 | [libsndfile-COPYING.txt](licenses/libsndfile-COPYING.txt) |
| sounddevice | 0.5.5 | MIT | [sounddevice-LICENSE.txt](licenses/sounddevice-LICENSE.txt) |
| PortAudio (sounddeviceが同梱) | — | MIT系 | [portaudio-README.md](licenses/portaudio-README.md) |
| pyworld (WORLDを含む) | 0.3.5 | MIT / BSD-3-Clause | [pyworld-LICENSE.txt](licenses/pyworld-LICENSE.txt) |
| ONNX Runtime | 1.27.0 | MIT | [onnxruntime-LICENSE.txt](licenses/onnxruntime-LICENSE.txt) |

## LGPL コンポーネントに関する注意

**Qt (PySide6/shiboken6)** と **libsndfile** は LGPL で提供されています。
本配布物ではこれらを独立したライブラリファイル（DLL / pyd）として同梱しており、
無改変で利用しています。利用者は同バージョンのライブラリに差し替えて
再実行することができます。ソースコードおよびライセンス全文の入手方法は
各ライセンスファイルに記載しています。

## 注記

- 上記バージョンは本 README 作成時点のビルドに含まれるものです。依存を更新して
  再ビルドした場合は、`licenses/` の内容と本一覧も更新してください。
- Python 標準ライブラリおよび CPython ランタイム (python3xx.dll 等) は
  Python Software Foundation License (PSF) で提供されています。
