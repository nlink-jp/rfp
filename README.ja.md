# rfp

[nlink-jp](https://github.com/nlink-jp) の新規プロジェクトの RFP（企画）プロセスを
ファシリテートする Claude Code Skill。対話的な Q&A で要件を収集し、
[CONVENTIONS.md](https://github.com/nlink-jp/.github/blob/main/CONVENTIONS.md)
Phase 1 に対する完全性を検証したうえで、構造化された RFP ドキュメントを生成します。

## インストール

### リリース zip から（推奨）

[Releases](https://github.com/nlink-jp/rfp/releases) から `rfp-vX.Y.Z.zip` を
ダウンロードし、skills ディレクトリに展開します:

```bash
unzip rfp-vX.Y.Z.zip -d ~/.claude/skills/
```

プロジェクト単位でインストールする場合は、プロジェクト内の
`.claude/skills/` に展開してください。

claude.ai / Claude Desktop / モバイルでは、**Settings → Skills** から
zip をそのままアップロードできます。

### ソースから

```bash
git clone https://github.com/nlink-jp/rfp.git
cd rfp
make install
```

`make install DEST=/path/to/project/.claude/skills` で特定プロジェクトに
インストールできます。`make uninstall` で削除します。

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
