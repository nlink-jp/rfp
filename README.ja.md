# rfp

[nlink-jp](https://github.com/nlink-jp) の新規プロジェクトの RFP（企画）プロセスを
ファシリテートする Claude Code Skill。対話的な Q&A で要件を収集し、
[CONVENTIONS.md](https://github.com/nlink-jp/.github/blob/main/CONVENTIONS.md)
Phase 1 に対する完全性を検証したうえで、構造化された RFP ドキュメントを生成します。

## インストール

[Releases](https://github.com/nlink-jp/rfp/releases) から
`rfp-vX.Y.Z.zip` をダウンロードし、登録する:

- **アプリから**（Claude Desktop / claude.ai / モバイル）— スキル設定
  （カスタマイズ → スキル）で zip を追加する。**この経路を推奨**。
  スキルの保存場所が変わっても影響を受けない。
- **Claude Code** — `unzip rfp-vX.Y.Z.zip -d ~/.claude/skills/`。
  プロジェクト単位なら、プロジェクト内の `.claude/skills/` に展開する。

チェックアウトから:

```bash
make install
```

リリース zip をビルドして**それを**展開するので、手元で動かすものと
リリースが配るものが一致する。パッケージングの欠陥は利用者に届く前に
手元のインストールを壊す。`make install DEST=/path/to/skills` で別の場所へ、
`make uninstall` で削除。

## 使い方

```
/rfp
/rfp my-new-tool
```

問題定義・機能仕様・設計判断・シリーズ配置・開発計画を順に確認し、
必要情報が揃った時点で RFP ドキュメントを出力します。

## 開発

```bash
make check     # 構造検証（frontmatter・相対リンク）
make package   # dist/rfp-vX.Y.Z.zip を生成（zip ルート = スキルフォルダ）
```

スキル本体は [`rfp/`](rfp/) にあります。このディレクトリだけが
`make package` の配布物・`make install` のコピー対象で、リポジトリの
scaffolding（README・Makefile・tests）は配布物に含まれません。

## 履歴

v0.1.0 以前、このスキルは
[skills-series](https://github.com/nlink-jp/skills-series) に含まれていました。
分割の経緯は
[ADR-004](https://github.com/nlink-jp/.github/blob/main/adr/004-skills-series-umbrella.md)
を参照してください。

## ドキュメント

- [English](README.md)
- [日本語](README.ja.md)

## ライセンス

[MIT](LICENSE)
