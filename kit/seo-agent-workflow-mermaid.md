# 🎁 SEO Agent Workflow（Mermaid）

6つの専門エージェントが共有メモリを介して回る、SEOループの全体像を描いた Mermaid 図。

**受け取り方**: 下のコードブロック右上のコピーボタンでコピーするか、このファイルをそのままダウンロードしてください。

**使い方**: GitHub / Notion / Obsidian など Mermaid 対応の場所にそのまま貼ると図として描画される。

```text
flowchart LR
    T([Trigger: cron / GSCアラート / 新規KW]) --> R[Research Agent<br/>KW・SERP・競合]
    R --> W[Writer Agent<br/>執筆 / 改稿]
    W --> RV[Reviewer Agent<br/>事実・E-E-A-T]
    RV --> SC[SEO Checker<br/>SEO/GEO・内部リンク]
    SC -->|指摘あり| W
    SC -->|OK| P[Publisher<br/>CMS入稿]
    P --> M[Monitor<br/>順位・CTR・index]
    M -->|下落検知| R
    M -->|記録| KB[(共有メモリ<br/>knowledge base)]
    KB -.読み込み.-> R
```

**ポイント**: SC -> W の戻り矢印が「品質ゲートを通るまで回す」ループの心臓部。
