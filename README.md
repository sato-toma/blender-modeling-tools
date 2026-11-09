# Blender Modeling Tools

Blenderに関するAgent向けSkillと技術資料を蓄積するリポジトリです。Blender MCPの具体的な機能は環境ごとに異なるため、利用可能なツールを確認してから操作します。

## 現在の内容

- [Blender Modeling Skill](./.agents/skills/blender-modeling/SKILL.md): Blenderでの作成・編集・検証・エクスポートの基本ワークフロー
- [知識マップ](./docs/knowledge-map.md): Blender技術を追加する場所と今後の整理方針
- [情報源と採用方針](./docs/sources.md): 公式資料の参照先、バージョン確認、出典記録のルール

## 方針

- Blender一般の知識・手順はこのリポジトリに集約します。
- Unity、Cluster、CCKなど特定プロジェクト固有の要件は、それぞれのプロジェクト側で管理します。
- 手順は利用中のBlenderバージョンとMCPの実際のツール仕様を確認してから適用します。
- 実行した操作と検証した結果を区別し、未確認の項目を成功扱いしません。
- 外部資料を転記する場合は、出典・確認日・ライセンスと再利用条件を確認します。

## Skillの配置

`.agents/skills/blender-modeling/` はAgent Skills形式のSkillです。利用するAgentが対応するSkillの導入方法に従って、このディレクトリをプロジェクトまたはユーザー領域に導入してください。インストーラーごとに指定方法が異なるため、特定のCLIコマンドはここでは仮定しません。

## ライセンス

このリポジトリには、現時点でライセンスを設定していません。公開リポジトリであること自体は、第三者による再利用許諾を意味しません。
