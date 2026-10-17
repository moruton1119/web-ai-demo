# Web AI Demo — ブラウザ内で動くAI実験場

もるラボの「サーバー計算ゼロ・秘密情報ゼロ」のWeb AI体験デモ。すべての推論は閲覧者のPCのブラウザ内で完結する完全静的サイト。

GitHub Pages: https://moruton1119.github.io/web-ai-demo/

## 構成

- `/` — ランディング(カード2枚)
- `/llm/` — ウェブLLMチャット。[naidan](https://github.com/nwtgck/naidan) v0.55.0 公式hosted配布物ベース(+PC専用ガード注入)
- `/image/` — ウェブ画像生成。SD-Turbo / ONNX Runtime Web + WebGPU(公式sd-turbo例ベースの自作実装)
- `mobile-block.html` — スマホからのアクセスに対する「PC専用」案内ページ(UA判定→リダイレクト)

## プライバシー設計

- サーバー計算なし・完全静的。APIキー・トークン等の秘密情報はリポジトリに一切含めない
- 入力内容はブラウザ外に送信されない(初回のみモデルファイルをHugging Face CDNから直接DL)
- LLM/画像生成ともにローカル動作のみ

## クレジット

- [naidan](https://github.com/nwtgck/naidan) by nwtgck (MIT License)
- [onnxruntime-inference-examples js/sd-turbo](https://github.com/microsoft/onnxruntime-inference-examples) by Microsoft (MIT License)
- 同梱サードパーティライセンス: `llm/llama-cpp-browser-native-licenses.txt`
