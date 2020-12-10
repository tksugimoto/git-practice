[TOP](../README.md)   
前: [実践](../basic/basic-practice.md)  
次: [他のブランチをマージ](./merge.md)  

---

# 3. 特定シチュエーションでの操作
Gitには、2章で行った基本的な操作の他にも特定シチュエーションで行う操作が複数あります。3章ではそれらの操作を取り上げます。  
3章のコンテンツは順不同で取り組んで構いません。また、必須ではありません。よりGitの操作に慣れたい方、実プロジェクトで必要になった方におすすめしています。

## 3-1. リモートリポジトリのブランチを取得
リモートリポジトリのブランチを取得するには`git fetch`を使います。`git fetch`を使うことでローカルリポジトリにリモート追跡ブランチが作成され、チェックアウトできるようになります。  
なお、ファイルやコードなどブランチの更新内容を取得するには`git pull`を使っていました。こちらでも`git fetch`と同等の処理が行われます。

1. 任意のディレクトリで`ターゲットリポジトリのクローンURL`を使いクローンしてください。
2. ブラウザで`ターゲットリポジトリのページ`にアクセスし、`master`プルダウンから`Find or create branch...`にブランチ名を入力し、`Create branch: <ブランチ名>`からリモートリポジトリに新しいブランチを作成してください。ブランチ名は「3-1」とします。
3. コンソールでリモート追跡ブランチを含む全てのブランチを表示し、手順2で作成したブランチがまだ反映されていないことを確認してください。（ヒント：`-a`オプションを使います）
4. リモートリポジトリのブランチを取得してください。
5. リモート追跡ブランチを含む全てのブランチを表示し、手順2で作成したブランチが反映されていることを確認してください。（ヒント：`-a`オプションを使います）
6. チェックアウトし、手順2で作成したブランチに切り替えられることを確認してください。（ヒント：切り替え先ブランチ名は、`remotes/origin/`は不要でブランチ名のみで構いません）
7. 現在のブランチを確認します。以下のようにブランチ「3-1」が選択されていることを確認してください。（他のブランチがリストされていても構いません）
   ```
   * 3-1
   master
   ```
8. ブラウザで`ターゲットリポジトリのページ`にアクセスし、`master`プルダウン右横の`branches`より、手順2で作成したリモートのブランチを削除してください。右側の赤いゴミ箱アイコンより削除可能です。
9.  チェックアウトし、masterブランチに切り替えてください。
10. 手順6で作成したローカルのブランチを削除してください。

--- 

[TOP](../README.md)   
前: [実践](../basic/basic-practice.md)  
次: [他のブランチをマージ](./merge.md)  