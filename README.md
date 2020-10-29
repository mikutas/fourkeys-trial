# fourkeys-trial

https://github.com/GoogleCloudPlatform/fourkeys

[エリート DevOps チームであることを Four Keys プロジェクトで確認する | Google Cloud Blog](https://cloud.google.com/blog/ja/products/gcp/using-the-four-keys-to-measure-your-devops-performance)

[Using the Four Keys to measure your DevOps performance | Google Cloud Blog](https://cloud.google.com/blog/products/devops-sre/using-the-four-keys-to-measure-your-devops-performance)

## メモ

- デプロイの頻度 - 組織による正常な本番環境へのリリースの頻度
- 変更のリードタイム - commit から本番環境稼働までの所要時間
- 変更障害率 - デプロイが原因で本番環境で障害が発生する割合（%）
  - Issueに原因コミットを記載することで測定可能になる
  - `root cause: コミットID`の形で記載する
- サービス復元時間 - 組織が本番環境での障害から回復するのにかかる時間
  - https://github.com/GoogleCloudPlatform/fourkeys/blame/e72fb57a796feab561e1a58b1d206731d869eccc/setup/INSTALL.md#L193
  - 障害の発生時刻は原因コミットを含むdeploymentが作成された時刻になる
  - 障害の解消時刻はIssueが閉じられた時刻になる

GitHubリポジトリと連携する場合、上2つの指標を測定するには`deployment`作成が、下2つの指標には`Incident`ラベルを付けたIssueのOpen/Closeが必要。

https://developer.github.com/webhooks/event-payloads/#deployment

https://developer.github.com/v3/repos/deployments/

hoge
