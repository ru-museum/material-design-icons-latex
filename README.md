material-design-icons-latex
==========

Material Design Icons for Latex.

- Latex で **[Material Design Icons(MDI) 4.0.0](https://github.com/google/material-design-icons/)**
 ( Google  ) を使用する為のライブラリーです。
- アイコン一覧は [**sample-list.pdf**](https://github.com/ru-museum/material-design-icons-latex/blob/main/sample-list.pdf) にあります（CheatSheet）。
- **著作権**を考慮しアイコンの実体は同梱していませんので各自ダウンロードして下さい。

### 作成環境
- LuaLatex  ( Debian：TexLive) 
- LuaLatex 及び BibLatex の導入方法、GEdit 及び VSCode による作業手順を  
 [LuaLaTeX & BibLaTeX with Debian：環境構築と作業手順の解説](https://github.com/ru-museum/material-design-icons-latex/blob/main/latex-with-debian.pdf) に解説しています。

### 動作確認
　**■ 先ず、simple-template.tex ファイルを使い動作確認を行って下さい。**  
　**■ これは gedit(GNOME) での設定例です。**

  1. simple-template.tex ファイルを編集し保存します。  
  2. 設定した「Alt + F5」でビルドしますと PDF ファイルその他の関連ファイルが生成されます。  
  3. 設定した「Shift + Alt + P」でPDF ファイルを開き確認します。  
  4. 再度編集保存し、ビルドしますと変更が反映されます。  
- 詳細は [LuaLaTeX & BibLaTeX with Debian：環境構築と作業手順の解説](https://github.com/ru-museum/material-design-icons-latex/blob/main/latex-with-debian.pdf) をご覧下さい。

### 利用手順
（１） [google /
material-design-icons](https://github.com/google/material-design-icons/) よりファイルをダウンロードします。  
（２） [ png ] フォルダ以下を下記の様に配置します。  
　　[ project ]   
　　　├── **material-icons**  
　  　　　（ [ png ]  の中身 ）  
  　 　　　├── action  
  　　 　　├── alert  

（３）アイコンデータファイルを読込ます。  
　　　**\usepackage{import}**  // 使用パッケージ  
　　　**\import{./lib/}{material-icons-data.tex}**

（４）アイコンの表示  
   - 入力値は **sample-list.pdf** を参照して下さい。  
　指定の prefix は "**md**" です。  
　　例： **\md**Home

- Latex のシステム上、コマンドに数字の使用が出来ませんので代替えの**英字**を使用しています。  
　例：**3d**Rotation → md**Thd**Rotation  
　　　Timer**10** → mdTimer**Ten**  

（５）サイズの指定  
　　　デフォルトでは **"1em**" が 指定されていますが変更可能です。  
　　　{**\fontsize{20pt}{14pt}\selectfont** \mdBuild}  
　　　※ **"14pt**" は行間値。   

（６）ビルド  
　　　lualatex template.tex  
　　　※ LuaLatex は直接 **PDF** ファイルが作成されます。

### エラー
- MDI のアップデート等によりアイコンファイルの実体が存在しないとビルドエラーとなります。  
→ ファイルへのパスを確認してデータファイルの修正を行って下さい。  

## 必要とするアイコンのみを使用する方法

（１）ダウンロードした ICON ファイルを下記の様に配置します。  
　[ project ]   
　　├── **material-icons**   
  　　 　├── **"build.png**" // 名前は適宜変更可  
  　 　　├── **"home.png**"  

（２）ICON の定義：  
　　\newcommand{**\mdBuild**}{\includegraphics[width=1em]{./material-icons/build.png}}
- 表示方法は「利用手順」と同様です。
- **\mdBuild** 部分は自由に指定可能です。
- **width=1em** で大きさを指定出来ます。

## CheatSheet として **sample-list.pdf** を独自に更新するには
   - **sample-list.tex** を編集、ビルドして下さい。

