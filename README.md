material-design-icons-latex
==========

Material Design Icons for Latex.

- Latex で **[Material Design Icons(MDI) 4.0.0](https://github.com/google/material-design-icons/)**
 ( Google  ) を使用する為のライブラリーです。
- アイコン一覧は [**sample-list.pdf**](https://github.com/ru-museum/material-design-icons-latex/blob/main/sample-list.pdf) にあります（CheatSheet）。  
PDF ファイルは画面右上の「Download」ボタンでダウンロードが出来ます。 
- **著作権**を考慮しアイコンの実体は同梱していませんので各自ダウンロードして下さい。

### 作成環境
- LuaLatex  ( Debian：TexLive) 
- LuaLatex 及び BibLatex の導入方法、gedit 及び VSCode による作業手順を  
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
```
[ project ]   
　　　├── material-icons  
　  　　　（ [ png ]  の中身 ）  
  　 　　　├── action  
  　　 　　├── alert  
```
（３）アイコンデータファイルを読込ます。  
```
\usepackage{import}  // 使用パッケージ  
\import{./lib/}{material-icons-data.tex}
```
（４）アイコンの表示  
   - 入力値は **sample-list.pdf** を参照して下さい。  
　指定の prefix は "**md**" です。  
```
\mdHome
```
- Latex のシステム上、コマンドに数字の使用が出来ませんので代替えの**英字**を使用しています。  
```
3dRotation → mdThdRotation  
Timer10 → mdTimerTen  
```
（５）サイズの指定  
　　　デフォルトでは **"1em**" が 指定されていますが変更可能です。  
```
　　　{\fontsize{20pt}{14pt}\selectfont \mdBuild}  
```
　　　※ **"14pt**" は行間値。 
   
- FONT-SIZE の定義も可能です。  
```
\def\fs#1{\fontsize{#1}{#1}\selectfont }  
\fs{30pt}{\mdSampleIcon}   
```
（６）ビルド  
```
　　　lualatex template.tex  
```
　　　※ LuaLatex は直接 **PDF** ファイルが作成されます。

### エラー
- MDI のアップデート等によりアイコンファイルの実体が存在しないとビルドエラーとなります。  
→ ファイルへのパスを確認してデータファイルの修正を行って下さい。  

## 必要とするアイコンのみを使用する方法

（１）ダウンロードした ICON ファイルを下記の様に配置します。  
```
　[ project ]   
　　├── material-icons   
  　　 　├── build.png // 名前は適宜変更可  
  　 　　├── home.png  
```
（２）ICON の定義：  
```
　　\newcommand{\mdBuild}{\includegraphics[width=1em]{./material-icons/build.png}}
```
- 表示方法は「利用手順」と同様です。
- **\mdBuild** 部分は自由に指定可能です。
- **width=1em** で大きさを指定出来ます。

## CheatSheet として **sample-list.pdf** を独自に更新するには
   - **sample-list.tex** を編集、ビルドして下さい。

***
### [English]

material-design-icons-latex.
=======================

Material Design Icons for Latex.

-  A library for using  [**Material Design Icons (MDI) 4.0.0**](https://github.com/google/material-design-icons/)(Google) with Latex.
-  The **sample-list.pdf** (CheatSheet).is the  list of icons,  
 You can download it by clicking the "Download" button at the top right of the screen.
-  **In consideration of copyright, the actual icons are not included, so please download them by yourself**.

How to Use
========
### Requirements

-  LuaLatex (Debian: TexLive)
-  How to install LuaLatex and BibLatex and how to work with gedit and VSCode:  
  See [LuaLaTeX & BibLaTeX with Debian](https://github.com/ru-museum/material-design-icons-latex/blob/main/latex-with-debian.pdf)(latex-with-debian.pdf).

### Before Usage

- First, check the operation using the **simple-template.tex**.  
- This is a example with gedit (GNOME) .  
    1. Edit and save the simple-template.tex file.  
    2. When you build with  "Alt + F5", PDF and other related files will be generated.  
    3. Open the PDF file with "Shift + Alt + P" and check it.  
    4. Edit and save it again and build it to reflect the changes.

    For details, see [LuaLaTeX & BibLaTeX with Debian](https://github.com/ru-museum/material-design-icons-latex/blob/main/latex-with-debian.pdf)(latex-with-debian.pdf).

### Usage 

1.  Download the file from [google/material-design-icons](https://github.com/google/material-design-icons/).
2. Place the following [png] folders as shown below.  
```
[Project]  
　├── material-icons  
   　　( Contents of [ png ])  
　　　├── action  
　　　├── alert  
```
3. Read the icon data file.  
```
\Usepackage{import} % used  package   
\Import{./lib/}{material-icons-data.tex}
```
4. Display icons  
The specified prefix is "**md**".  
```
\mdHome
```
-    Please refer to **sample-list.pdf** for the input value.   
-    Due to the Latex system, numbers cannot be used in commands, so alternative alphabetic characters are used.  
```
3dRotation → mdThdRotation  
Timer10 → mdTimerTen
```
5. Specifying the size  
By default, "1em", but you can change it.   
```
{\Fontsize{20pt}{14pt}\selectfont \mdBuild}
```
* "**14pt**" is the line spacing value.

- You can also below:  
```
\def\fs#1{\fontsize{#1}{#1}\selectfont }  
\fs{30pt}{\mdSampleIcon}   
```
6. Build  
```
lualatex template.tex
```
- LuaLatex creates a PDF file directly.

### Error

- If the icon file does not exist due to MDI update etc., a build error will occur.  
    → Check the path to the file and correct the data file.

### How to use only the icons you need

1.  Place the downloaded icon-files as shown below.  
```
[Project]  
　├── material-icons  
　　├── build.png // Name can be changed as appropriate  
　　├── home.png
```
2. Definition of ICON:
```
\newcommand{\mdBuild}{\includegraphics[width=1em]{./material-icons/build.png}}
```
- The display method is the same in **Usage**.
- The \\**mdBuild** part can be specified freely.
- You can specify the size with **width=1em**.

### Update sample-list.pdf independently as CheatSheet
Edit and build **sample-list.tex**.


