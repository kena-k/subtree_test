# subtree_test


Git Subtreeの使い方（1つのリポジトリで完結させる方法）

1. 取り込み元を作成する（今回はdevelopブランチ）
 git checkout -b develop
 ※この時、取り込み先のリポジトリを管理するためのフォルダは作成する必要なし

2. 取り込み先を作成する
 git checkout -b subtree_a
 mkdir ModuleA
 touch ModuleA/touch

3. 取り込み先をリモートにプッシュする
 git add ~~
 git commit -m ~~
 git push origin subtree_a
→リモートにサブツリー用のリポジトリが完成
 基本的なGit Subtreeの使用方法は取り込み先のプロジェクトのリポジトリに、
 別プロジェクトのリポジトリを取り込む
 今回のsubtree_aブランチが別プロジェクトのリポジトリに当たる。

4. 取り込み先へsubtreeを取り込む
 git subtree add --prefix SubtreeModuleA（リポジトリ管理用フォルダ） subtree_a
→これで取り込み成功
 見つからない場合は、別ファイルを一度コミットして確かめてみるとよい

連携完了後の進め方
1. 取り込み先のブランチでコミットし続ける
2. 作成完了したらレビュー依頼
3. 問題なければ取り込み元へ更新する
 (developブランチで) git subtree merge --prefix SubtreeModuleA subtree_a

