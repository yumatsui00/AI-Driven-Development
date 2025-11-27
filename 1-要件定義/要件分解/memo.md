要件分解では要件の分解と、依存関係の整理を行う

依存関係
1. データモデルの依存関係　ex)project→board→list→task
2. page遷移の依存関係 /home/project/[id]/boards/[id] みたいな依存関係
3. ロジックの依存関係
    projectロジック：create, delete, list
    この内、create, listはboardsに依存はしないが、delete時boardを消す必要がある
    →deleteは基本最後に作成する必要がある
4. UIの依存関係
    リストの並び替えはboardページが完成していれば動く
    しかし、リスト間のtaskの移動はlistが完成していないと無理

middlewareは全ページをラップする（保護する）ため全てに依存しない



並列処理を行うに当たり、完全並列可能なもの、mockデータがあれば並列可能なもの（後回しでも良い）、mockがあっても並列不可能なものがある
基本的にはそれに従って要件分解時に依存関係整理も行う