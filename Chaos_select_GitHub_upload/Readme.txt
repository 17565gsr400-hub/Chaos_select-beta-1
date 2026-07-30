Chaos_select beta
配布版 README

【概要】
Chaos_select は、指定したフォルダの直下にあるファイルまたはフォルダから
ランダムに1件を選び、Windows Explorer上で選択状態にする小型ツールです。

本ツールは対象を削除、移動、名前変更、実行しません。
選ばれた項目をExplorer上で選択状態にするだけです。

【動作環境】
・64bit版 Windows
・Windows Explorer

環境によっては、Microsoft Visual C++ ランタイムが必要になる場合があります。

【配布ファイル】
Chaos_select.exe
  フォルダそのものを右クリックして使う版です。

Chaos_select_D.exe
  フォルダ内の空白部分を右クリックして使う版です。

Chaos_select.reg
  フォルダ右クリック版を現在のユーザーに登録します。

Chaos_select_D.reg
  フォルダ内の空白部分右クリック版を現在のユーザーに登録します。

uninstall_Chaos_select.reg
  Chaos_select関連の右クリックメニュー登録を削除します。

README.md
  GitHub向けの詳細説明書です。

regファイル原文
  各REGファイルの内容をTXT形式で確認するためのフォルダです。

※現行配布版にC言語ソースコードとビルドスクリプトは含まれていません。

【設置場所】
この配布版は、以下の場所に配置する前提です。

C:\Chaos_select

配置例：
C:\Chaos_select\Chaos_select.exe
C:\Chaos_select\Chaos_select_D.exe
C:\Chaos_select\Chaos_select.reg
C:\Chaos_select\Chaos_select_D.reg
C:\Chaos_select\uninstall_Chaos_select.reg

別の場所に置く場合は、各REGファイル内の
C:\\Chaos_select\\... のパスを書き換えてから登録してください。

【登録方法】
1. Chaos_selectフォルダを C:\Chaos_select に置きます。
2. Chaos_select.reg をダブルクリックすると、フォルダ右クリック版が登録されます。
3. Chaos_select_D.reg をダブルクリックすると、フォルダ内の空白部分版が登録されます。
4. Windowsの確認画面が表示された場合は、内容を確認してから許可してください。

両方の操作方法を使う場合は、2つとも登録してください。

【使い方】
フォルダ右クリック版：
1. 対象フォルダを右クリックします。
2. Chaos_select を選びます。
3. フォルダ直下からランダムに1件が選ばれます。

フォルダ内の空白部分版：
1. 対象フォルダをExplorerで開きます。
2. ファイルがない空白部分を右クリックします。
3. Chaos_select_D を選びます。
4. 開いているフォルダの直下からランダムに1件が選ばれます。

【登録解除】
uninstall_Chaos_select.reg をダブルクリックしてください。

削除されるのは、現在のユーザーに登録された右クリックメニューだけです。
C:\Chaos_select フォルダ内のファイルは自動では削除されません。
不要な場合は手動で削除してください。

【現在の仕様と制限】
・探索対象は指定フォルダの直下1階層だけです。
・サブフォルダ内部の再帰探索は行いません。
・保持できる候補は最大1024件です。
・MAX_PATHを超える長いパスには対応していません。
・ANSI版Windows APIを使用しています。
・日本語や特殊文字を含むパスでは、環境によって失敗する可能性があります。
・同じ秒に連続実行すると、同じ対象が選ばれやすい場合があります。
・暗号学的な乱数や厳密な抽選には使用できません。
・対象フォルダが空の場合、選択は行われません。
・実行ファイルにはデジタル署名が付与されていません。

【レジストリ登録先】
HKEY_CURRENT_USER\Software\Classes\Directory\shell\Chaos_select
HKEY_CURRENT_USER\Software\Classes\Directory\Background\shell\Chaos_select_D

現在のWindowsユーザーだけに適用されます。

【トラブルシューティング】
右クリックメニューが表示されない場合：
・C:\Chaos_select にEXEが存在するか確認してください。
・REGファイル内のパスと実際の配置場所が一致しているか確認してください。
・ExplorerまたはWindowsを再起動してください。

実行しても選択されない場合：
・対象フォルダが空でないか確認してください。
・短いパスのテスト用フォルダで試してください。
・日本語や特殊文字を含まないパスで試してください。


【注意】
この配布版はベータ版です。
重要な作業環境へ導入する前に、テスト用フォルダで動作を確認してください。
