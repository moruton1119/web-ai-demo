# Web AI Demo — 画像生成(ブラウザ内で動くAI実験場)

もるラボの「サーバー計算ゼロ・秘密情報ゼロ」のWeb AI体験デモ。すべての推論は閲覧者のPCのブラウザ内で完結する完全静的サイト。

GitHub Pages: https://moruton1119.github.io/web-ai-demo/

## 構成

- `/` — ランディング(カード)
- `/image/` — ウェブ画像生成。SD-Turbo / ONNX Runtime Web + WebGPU(公式sd-turbo例ベースの自作実装)
  - **日本語プロンプト対応**: 日本語を検知するとローカル翻訳モデル(opus-mt-ja-en)で英語に自動翻訳してから生成。翻訳もすべてブラウザ内
- `mobile-block.html` — スマホからのアクセスに対する「PC専用」案内ページ(UA判定→リダイレクト)

LLMチャットはサイト単位で別リポジトリに分割: [web-llm-demo](https://github.com/moruton1119/web-llm-demo) (https://moruton1119.github.io/web-llm-demo/)

## プライバシー設計

- サーバー計算なし・完全静的。APIキー・トークン等の秘密情報はリポジトリに一切含めない
- 入力内容はブラウザ外に送信されない(初回のみモデルファイルをHugging Face CDNから直接DL)
- 画像生成・翻訳ともにローカル動作のみ

## クレジット

- [onnxruntime-inference-examples js/sd-turbo](https://github.com/microsoft/onnxruntime-inference-examples) by Microsoft (MIT License)
- [opus-mt-ja-en](https://huggingface.co/Xenova/opus-mt-ja-en) (Helsinki-NLP opus-mt / CC-BY-4.0)
