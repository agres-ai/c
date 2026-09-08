# c — 出勤簿QRの転送ページ

外国人出勤簿PDFのQRコードの飛び先。Google Apps Scriptの確認画面へ転送するだけの静的ページ。

QRの飛び先をGASのexec URLに直接していたところ、スマホのQRリーダー（Googleアプリ/レンズ）が
「Googleのリンク」と認識してログイン中のアカウント番号を `/macros/u/<番号>/s/...` の形で
差し込んでしまい、404「ページが見つかりません」になる不具合があった（2026-09-08）。
Google以外のドメインを経由させることで、この書き換えを回避している。

生成側は agres-ai/roumu の `tools/sheets/export_attendance_pdf.js`。
