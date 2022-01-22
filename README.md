material-design-icons-latex
==========

Material Design Icons for Latex.

## == 準備中です== 

- Latex で **[Material Design Icons(MDI) 4.0.0](https://github.com/google/material-design-icons/)**
 ( Google  ) を使用する為のライブラリーです。
- アイコン一覧(CheatSheet)は **sample-list.pdf** にあります。
- **著作権**を考慮しアイコンの実体は同梱していませんので各自ダウンロードして下さい。

### 作成環境
- LuaLatex  ( Debian：TexLive) 
- LuaLatex 及び BibLatex の導入方法、GEdit 及び VSCode による作業手順を Help.pdf（準備中）に解説しています。

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
  　　 　├── **"build.png**" // 名前は適時変更可  
  　 　　├── **"home.png**"  

（２）ICON の定義：  
　　\newcommand{**\mdBuild**}{\includegraphics[width=1em]{./material-icons/build.png}}
- 表示方法は「利用手順」と同様です。
- **\mdBuild** 部分は自由に指定可能です。
- **width=1em** で大きさを指定出来ます。

## CheatSheet として **sample-list.pdf** を独自に更新するには
   - **sample-list.tex** を編集、ビルドして下さい。

