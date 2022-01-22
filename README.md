material-design-icons-latex
==========

Latex 用 Material Design Icons

## == 準備中です== 

- Latex で **Material Design Icons 4.0.0** ( Google  ) を使用する為のライブラリーです。

### 作成環境
- LuaLatex  ( Debian：TexLive) 
- Lualatex 及び BibLatex の導入方法、GEdit 及び VSCode による作業手順を Help.pdf に解説しています。

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
　　**\import{./}{material-icons-data.tex}**

（４）アイコンの表示  
　　指定の prefix は "**md**" です。  
　　　例： **\md**Home

（５）サイズの指定
　デフォルトでは **"1em**" が 指定されていますが変更可能です。  
　{**\fontsize{20pt}{14pt}\selectfont** \mdBuild} 

（６）ビルド
　　Lualatex pproject.tex

### 【注意】
-  Latex のシステム上コマンドに数字は使用出来ませんので、代替えの英字を使用しています。  
　例：**3d**Rotation → md**Thd**Rotation  
　　　Timer**10** → mdTimer**Ten**  

## 必要とするアイコンのみを使用する方法

（１）ダウンロードした ICON ファイルを下記の様に配置します。  
　[ project ]   
　　├── **material-icons**   
  　　 　├── **"build.png**"  
  　 　　├── **"home.png**"  

（２）ICON の定義：  
　　\newcommand{**\mdBuild**}{\includegraphics[width=1em]{./material-icons/build.png}}
- 表示方法は「利用手順」と同様です。
- **\mdBuild** 部分は自由に指定可能です。
- **width=1em** で大きさの指定が可能です。


### リンク

