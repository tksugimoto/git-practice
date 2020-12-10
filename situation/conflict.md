[TOP](../README.md)   
前: [他のブランチをマージ](./merge.md)  
次: [コミットの取消・打消](./reset-revert.md)  

---

# 3. 特定シチュエーションでの操作
## 3-3. マージ時の競合解決
異なるブランチで同じファイルの同じ行に対して修正を行うと、競合（コンフリクト）となりマージができなくなります。  
競合を解決するためには、競合が発生しなくなるまでブランチのファイルを編集するか、GitLabやGitHubのWebUIを使用する方法があります。今回はブランチのファイルを編集する方法で競合を解決します。  

今回は以下のような特徴を持つ2つのブランチを作成し、マージ時に競合（コンフリクト）を発生させてみます。  
- ブランチ「3-3-source」では「3-3.txt」を作り、このファイルを変更したコミットを作ります。
- ブランチ「3-3-target」では「3-3.txt」を作り、このファイルを「3-3-source」とは別の内容で変更したコミットを作ります。


1. 任意のディレクトリで`ターゲットリポジトリのクローンURL`を使いクローンしてください。
2. コンソールで新しいブランチ「3-3-source」を作成し、切り替えてください。
3. 現在のブランチを確認します。以下のようにブランチ「3-3-source」が選択されていることを確認してください。（他のブランチがリストされていても構いません）
   ```
   * 3-3-source
   master
   ```
4. ファイル「3-3.txt」を以下の内容で作成して、コミットしてください。
```
year: 2020
month: 09
day: 18

---

minute: 16
```
4. ブランチ「master」に切り替えてください。
5. コンソールで新しいブランチ「3-3-target」を作成し、切り替えてください。
6. 現在のブランチを確認します。以下のようにブランチ「3-3-target」が選択されていることを確認してください。（他のブランチがリストされていても構いません）
   ```
   * 3-3-target
   3-3-source
   master
   ```
7. ファイル「3-3.txt」を以下の内容で作成して、コミットしてください。手順4で作成した内容と一部競合する行が存在しています。
```
year: 2025
month: 12
day: 18

---
hour: 13
minute: 16
```
6. そのままブランチ「3-3-target」で、ブランチ「3-3-source」をマージしてください。以下のような出力になります。
```
CONFLICT (add/add): Merge conflict in 3-3/3-3.txt
Auto-merging 3-3/3-3.txt
Automatic merge failed; fix conflicts and then commit the result.
```
7. ファイル「3-3.txt」を開くと以下のようなコンフリクトが発生しています。
```
<<<<<<< HEAD
year: 2025
month: 12
day: 18

---
hour: 13
minute: 16
=======
year: 2020
month: 09
day: 18

---

minute: 16

>>>>>>> 3-3-source

```
8. `<<<<<<< HEAD`から`>>>>>>> 3-3-source`で囲まれた部分を以下のように編集してください。ここでは両方の変更をうまく残してみます。なお、`<<<<<<< HEAD`から`>>>>>>> 3-3-source`の部分は削除して構いません。
```
year: 2020
month: 09
day: 18

---
hour: 13
minute: 16
```
9. これで競合は解決され、マージ完了です。ファイル「3-3.txt」をコミットしてください。
10. ブランチ「3-3-source」、「3-3-target」を削除してください。

--- 

[TOP](../README.md)   
前: [他のブランチをマージ](./merge.md)  
次: [コミットの取消・打消](./reset-revert.md)  