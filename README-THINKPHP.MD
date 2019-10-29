#thinkphp5.1整合editor.md

![](https://pandao.github.io/editor.md/images/logos/editormd-logo-180x180.png)
![](https://img.shields.io/github/stars/pandao/editor.md.svg)![](https://img.shields.io/github/forks/pandao/editor.md.svg)![](https://img.shields.io/github/tag/pandao/editor.md.svg)![](https://img.shields.io/github/release/pandao/editor.md.svg) ![](https://img.shields.io/github/issues/pandao/editor.md.svg) ![](https://img.shields.io/bower/v/editor.md.svg)

**目录 (Table of Contents)**

[TOCM]

[TOC]



- ## 1.editor.md获取地址：
- https://github.com/pandao/editor.md.git

 - ## 2.安装准备
 - 包中文件较多 我这里只用了需要的文件
| css  | fonts  | images  | languages  |  lib |  plugins |  editormd.js |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|   |   |   |   |   |   |   |   |
---
###文件树：
```shell
guyezi@guyezideiMac editor.md-master % tree
.
├── css
│   ├── editormd.css
│   ├── editormd.logo.css
│   ├── editormd.logo.min.css
│   ├── editormd.min.css
│   ├── editormd.preview.css
│   └── editormd.preview.min.css
├── editormd.js
├── fonts
│   ├── FontAwesome.otf
│   ├── editormd-logo.eot
│   ├── editormd-logo.svg
│   ├── editormd-logo.ttf
│   ├── editormd-logo.woff
│   ├── fontawesome-webfont.eot
│   ├── fontawesome-webfont.svg
│   ├── fontawesome-webfont.ttf
│   ├── fontawesome-webfont.woff
│   └── fontawesome-webfont.woff2
├── images
│   ├── loading.gif
│   ├── loading@2x.gif
│   ├── loading@3x.gif
│   └── logos
│       ├── editormd-favicon-16x16.ico
│       ├── editormd-favicon-24x24.ico
│       ├── editormd-favicon-32x32.ico
│       ├── editormd-favicon-48x48.ico
│       ├── editormd-favicon-64x64.ico
│       ├── editormd-logo-114x114.png
│       ├── editormd-logo-120x120.png
│       ├── editormd-logo-144x144.png
│       ├── editormd-logo-16x16.png
│       ├── editormd-logo-180x180.png
│       ├── editormd-logo-240x240.png
│       ├── editormd-logo-24x24.png
│       ├── editormd-logo-320x320.png
│       ├── editormd-logo-32x32.png
│       ├── editormd-logo-48x48.png
│       ├── editormd-logo-57x57.png
│       ├── editormd-logo-64x64.png
│       ├── editormd-logo-72x72.png
│       ├── editormd-logo-96x96.png
│       └── vi.png
├── languages
│   ├── en.js
│   └── zh-tw.js
├── lib
│   ├── codemirror
│   │   ├── AUTHORS
│   │   ├── LICENSE
│   │   ├── README.md
│   │   ├── addon
│   │   │   ├── comment
│   │   │   │   ├── comment.js
│   │   │   │   └── continuecomment.js
│   │   │   ├── dialog
│   │   │   │   ├── dialog.css
│   │   │   │   └── dialog.js
│   │   │   ├── display
│   │   │   │   ├── fullscreen.css
│   │   │   │   ├── fullscreen.js
│   │   │   │   ├── panel.js
│   │   │   │   ├── placeholder.js
│   │   │   │   └── rulers.js
│   │   │   ├── edit
│   │   │   │   ├── closebrackets.js
│   │   │   │   ├── closetag.js
│   │   │   │   ├── continuelist.js
│   │   │   │   ├── matchbrackets.js
│   │   │   │   ├── matchtags.js
│   │   │   │   └── trailingspace.js
│   │   │   ├── fold
│   │   │   │   ├── brace-fold.js
│   │   │   │   ├── comment-fold.js
│   │   │   │   ├── foldcode.js
│   │   │   │   ├── foldgutter.css
│   │   │   │   ├── foldgutter.js
│   │   │   │   ├── indent-fold.js
│   │   │   │   ├── markdown-fold.js
│   │   │   │   └── xml-fold.js
│   │   │   ├── hint
│   │   │   │   ├── anyword-hint.js
│   │   │   │   ├── css-hint.js
│   │   │   │   ├── html-hint.js
│   │   │   │   ├── javascript-hint.js
│   │   │   │   ├── show-hint.css
│   │   │   │   ├── show-hint.js
│   │   │   │   ├── sql-hint.js
│   │   │   │   └── xml-hint.js
│   │   │   ├── lint
│   │   │   │   ├── coffeescript-lint.js
│   │   │   │   ├── css-lint.js
│   │   │   │   ├── javascript-lint.js
│   │   │   │   ├── json-lint.js
│   │   │   │   ├── lint.css
│   │   │   │   ├── lint.js
│   │   │   │   └── yaml-lint.js
│   │   │   ├── merge
│   │   │   │   ├── merge.css
│   │   │   │   └── merge.js
│   │   │   ├── mode
│   │   │   │   ├── loadmode.js
│   │   │   │   ├── multiplex.js
│   │   │   │   ├── multiplex_test.js
│   │   │   │   ├── overlay.js
│   │   │   │   └── simple.js
│   │   │   ├── runmode
│   │   │   │   ├── colorize.js
│   │   │   │   ├── runmode-standalone.js
│   │   │   │   ├── runmode.js
│   │   │   │   └── runmode.node.js
│   │   │   ├── scroll
│   │   │   │   ├── annotatescrollbar.js
│   │   │   │   ├── scrollpastend.js
│   │   │   │   ├── simplescrollbars.css
│   │   │   │   └── simplescrollbars.js
│   │   │   ├── search
│   │   │   │   ├── match-highlighter.js
│   │   │   │   ├── matchesonscrollbar.css
│   │   │   │   ├── matchesonscrollbar.js
│   │   │   │   ├── search.js
│   │   │   │   └── searchcursor.js
│   │   │   ├── selection
│   │   │   │   ├── active-line.js
│   │   │   │   ├── mark-selection.js
│   │   │   │   └── selection-pointer.js
│   │   │   ├── tern
│   │   │   │   ├── tern.css
│   │   │   │   ├── tern.js
│   │   │   │   └── worker.js
│   │   │   └── wrap
│   │   │       └── hardwrap.js
│   │   ├── addons.min.js
│   │   ├── bower.json
│   │   ├── codemirror.min.css
│   │   ├── codemirror.min.js
│   │   ├── lib
│   │   │   ├── codemirror.css
│   │   │   └── codemirror.js
│   │   ├── mode
│   │   │   ├── apl
│   │   │   │   ├── apl.js
│   │   │   │   └── index.html
│   │   │   ├── asterisk
│   │   │   │   ├── asterisk.js
│   │   │   │   └── index.html
│   │   │   ├── clike
│   │   │   │   ├── clike.js
│   │   │   │   ├── index.html
│   │   │   │   └── scala.html
│   │   │   ├── clojure
│   │   │   │   ├── clojure.js
│   │   │   │   └── index.html
│   │   │   ├── cobol
│   │   │   │   ├── cobol.js
│   │   │   │   └── index.html
│   │   │   ├── coffeescript
│   │   │   │   ├── coffeescript.js
│   │   │   │   └── index.html
│   │   │   ├── commonlisp
│   │   │   │   ├── commonlisp.js
│   │   │   │   └── index.html
│   │   │   ├── css
│   │   │   │   ├── css.js
│   │   │   │   ├── index.html
│   │   │   │   ├── less.html
│   │   │   │   ├── less_test.js
│   │   │   │   ├── scss.html
│   │   │   │   ├── scss_test.js
│   │   │   │   └── test.js
│   │   │   ├── cypher
│   │   │   │   ├── cypher.js
│   │   │   │   └── index.html
│   │   │   ├── d
│   │   │   │   ├── d.js
│   │   │   │   └── index.html
│   │   │   ├── dart
│   │   │   │   ├── dart.js
│   │   │   │   └── index.html
│   │   │   ├── diff
│   │   │   │   ├── diff.js
│   │   │   │   └── index.html
│   │   │   ├── django
│   │   │   │   ├── django.js
│   │   │   │   └── index.html
│   │   │   ├── dockerfile
│   │   │   │   ├── dockerfile.js
│   │   │   │   └── index.html
│   │   │   ├── dtd
│   │   │   │   ├── dtd.js
│   │   │   │   └── index.html
│   │   │   ├── dylan
│   │   │   │   ├── dylan.js
│   │   │   │   └── index.html
│   │   │   ├── ebnf
│   │   │   │   ├── ebnf.js
│   │   │   │   └── index.html
│   │   │   ├── ecl
│   │   │   │   ├── ecl.js
│   │   │   │   └── index.html
│   │   │   ├── eiffel
│   │   │   │   ├── eiffel.js
│   │   │   │   └── index.html
│   │   │   ├── erlang
│   │   │   │   ├── erlang.js
│   │   │   │   └── index.html
│   │   │   ├── forth
│   │   │   │   ├── forth.js
│   │   │   │   └── index.html
│   │   │   ├── fortran
│   │   │   │   ├── fortran.js
│   │   │   │   └── index.html
│   │   │   ├── gas
│   │   │   │   ├── gas.js
│   │   │   │   └── index.html
│   │   │   ├── gfm
│   │   │   │   ├── gfm.js
│   │   │   │   ├── index.html
│   │   │   │   └── test.js
│   │   │   ├── gherkin
│   │   │   │   ├── gherkin.js
│   │   │   │   └── index.html
│   │   │   ├── go
│   │   │   │   ├── go.js
│   │   │   │   └── index.html
│   │   │   ├── groovy
│   │   │   │   ├── groovy.js
│   │   │   │   └── index.html
│   │   │   ├── haml
│   │   │   │   ├── haml.js
│   │   │   │   ├── index.html
│   │   │   │   └── test.js
│   │   │   ├── haskell
│   │   │   │   ├── haskell.js
│   │   │   │   └── index.html
│   │   │   ├── haxe
│   │   │   │   ├── haxe.js
│   │   │   │   └── index.html
│   │   │   ├── htmlembedded
│   │   │   │   ├── htmlembedded.js
│   │   │   │   └── index.html
│   │   │   ├── htmlmixed
│   │   │   │   ├── htmlmixed.js
│   │   │   │   └── index.html
│   │   │   ├── http
│   │   │   │   ├── http.js
│   │   │   │   └── index.html
│   │   │   ├── idl
│   │   │   │   ├── idl.js
│   │   │   │   └── index.html
│   │   │   ├── index.html
│   │   │   ├── jade
│   │   │   │   ├── index.html
│   │   │   │   └── jade.js
│   │   │   ├── javascript
│   │   │   │   ├── index.html
│   │   │   │   ├── javascript.js
│   │   │   │   ├── json-ld.html
│   │   │   │   ├── test.js
│   │   │   │   └── typescript.html
│   │   │   ├── jinja2
│   │   │   │   ├── index.html
│   │   │   │   └── jinja2.js
│   │   │   ├── julia
│   │   │   │   ├── index.html
│   │   │   │   └── julia.js
│   │   │   ├── kotlin
│   │   │   │   ├── index.html
│   │   │   │   └── kotlin.js
│   │   │   ├── livescript
│   │   │   │   ├── index.html
│   │   │   │   └── livescript.js
│   │   │   ├── lua
│   │   │   │   ├── index.html
│   │   │   │   └── lua.js
│   │   │   ├── markdown
│   │   │   │   ├── index.html
│   │   │   │   ├── markdown.js
│   │   │   │   └── test.js
│   │   │   ├── meta.js
│   │   │   ├── mirc
│   │   │   │   ├── index.html
│   │   │   │   └── mirc.js
│   │   │   ├── mllike
│   │   │   │   ├── index.html
│   │   │   │   └── mllike.js
│   │   │   ├── modelica
│   │   │   │   ├── index.html
│   │   │   │   └── modelica.js
│   │   │   ├── nginx
│   │   │   │   ├── index.html
│   │   │   │   └── nginx.js
│   │   │   ├── ntriples
│   │   │   │   ├── index.html
│   │   │   │   └── ntriples.js
│   │   │   ├── octave
│   │   │   │   ├── index.html
│   │   │   │   └── octave.js
│   │   │   ├── pascal
│   │   │   │   ├── index.html
│   │   │   │   └── pascal.js
│   │   │   ├── pegjs
│   │   │   │   ├── index.html
│   │   │   │   └── pegjs.js
│   │   │   ├── perl
│   │   │   │   ├── index.html
│   │   │   │   └── perl.js
│   │   │   ├── php
│   │   │   │   ├── index.html
│   │   │   │   ├── php.js
│   │   │   │   └── test.js
│   │   │   ├── pig
│   │   │   │   ├── index.html
│   │   │   │   └── pig.js
│   │   │   ├── properties
│   │   │   │   ├── index.html
│   │   │   │   └── properties.js
│   │   │   ├── puppet
│   │   │   │   ├── index.html
│   │   │   │   └── puppet.js
│   │   │   ├── python
│   │   │   │   ├── index.html
│   │   │   │   └── python.js
│   │   │   ├── q
│   │   │   │   ├── index.html
│   │   │   │   └── q.js
│   │   │   ├── r
│   │   │   │   ├── index.html
│   │   │   │   └── r.js
│   │   │   ├── rpm
│   │   │   │   ├── changes
│   │   │   │   │   └── index.html
│   │   │   │   ├── index.html
│   │   │   │   └── rpm.js
│   │   │   ├── rst
│   │   │   │   ├── index.html
│   │   │   │   └── rst.js
│   │   │   ├── ruby
│   │   │   │   ├── index.html
│   │   │   │   ├── ruby.js
│   │   │   │   └── test.js
│   │   │   ├── rust
│   │   │   │   ├── index.html
│   │   │   │   └── rust.js
│   │   │   ├── sass
│   │   │   │   ├── index.html
│   │   │   │   └── sass.js
│   │   │   ├── scheme
│   │   │   │   ├── index.html
│   │   │   │   └── scheme.js
│   │   │   ├── shell
│   │   │   │   ├── index.html
│   │   │   │   ├── shell.js
│   │   │   │   └── test.js
│   │   │   ├── sieve
│   │   │   │   ├── index.html
│   │   │   │   └── sieve.js
│   │   │   ├── slim
│   │   │   │   ├── index.html
│   │   │   │   ├── slim.js
│   │   │   │   └── test.js
│   │   │   ├── smalltalk
│   │   │   │   ├── index.html
│   │   │   │   └── smalltalk.js
│   │   │   ├── smarty
│   │   │   │   ├── index.html
│   │   │   │   └── smarty.js
│   │   │   ├── smartymixed
│   │   │   │   ├── index.html
│   │   │   │   └── smartymixed.js
│   │   │   ├── solr
│   │   │   │   ├── index.html
│   │   │   │   └── solr.js
│   │   │   ├── soy
│   │   │   │   ├── index.html
│   │   │   │   └── soy.js
│   │   │   ├── sparql
│   │   │   │   ├── index.html
│   │   │   │   └── sparql.js
│   │   │   ├── spreadsheet
│   │   │   │   ├── index.html
│   │   │   │   └── spreadsheet.js
│   │   │   ├── sql
│   │   │   │   ├── index.html
│   │   │   │   └── sql.js
│   │   │   ├── stex
│   │   │   │   ├── index.html
│   │   │   │   ├── stex.js
│   │   │   │   └── test.js
│   │   │   ├── stylus
│   │   │   │   ├── index.html
│   │   │   │   └── stylus.js
│   │   │   ├── tcl
│   │   │   │   ├── index.html
│   │   │   │   └── tcl.js
│   │   │   ├── textile
│   │   │   │   ├── index.html
│   │   │   │   ├── test.js
│   │   │   │   └── textile.js
│   │   │   ├── tiddlywiki
│   │   │   │   ├── index.html
│   │   │   │   ├── tiddlywiki.css
│   │   │   │   └── tiddlywiki.js
│   │   │   ├── tiki
│   │   │   │   ├── index.html
│   │   │   │   ├── tiki.css
│   │   │   │   └── tiki.js
│   │   │   ├── toml
│   │   │   │   ├── index.html
│   │   │   │   └── toml.js
│   │   │   ├── tornado
│   │   │   │   ├── index.html
│   │   │   │   └── tornado.js
│   │   │   ├── turtle
│   │   │   │   ├── index.html
│   │   │   │   └── turtle.js
│   │   │   ├── vb
│   │   │   │   ├── index.html
│   │   │   │   └── vb.js
│   │   │   ├── vbscript
│   │   │   │   ├── index.html
│   │   │   │   └── vbscript.js
│   │   │   ├── velocity
│   │   │   │   ├── index.html
│   │   │   │   └── velocity.js
│   │   │   ├── verilog
│   │   │   │   ├── index.html
│   │   │   │   ├── test.js
│   │   │   │   └── verilog.js
│   │   │   ├── xml
│   │   │   │   ├── index.html
│   │   │   │   ├── test.js
│   │   │   │   └── xml.js
│   │   │   ├── xquery
│   │   │   │   ├── index.html
│   │   │   │   ├── test.js
│   │   │   │   └── xquery.js
│   │   │   ├── yaml
│   │   │   │   ├── index.html
│   │   │   │   └── yaml.js
│   │   │   └── z80
│   │   │       ├── index.html
│   │   │       └── z80.js
│   │   ├── modes.min.js
│   │   ├── package.json
│   │   └── theme
│   │       ├── 3024-day.css
│   │       ├── 3024-night.css
│   │       ├── ambiance-mobile.css
│   │       ├── ambiance.css
│   │       ├── base16-dark.css
│   │       ├── base16-light.css
│   │       ├── blackboard.css
│   │       ├── cobalt.css
│   │       ├── colorforth.css
│   │       ├── eclipse.css
│   │       ├── elegant.css
│   │       ├── erlang-dark.css
│   │       ├── lesser-dark.css
│   │       ├── mbo.css
│   │       ├── mdn-like.css
│   │       ├── midnight.css
│   │       ├── monokai.css
│   │       ├── neat.css
│   │       ├── neo.css
│   │       ├── night.css
│   │       ├── paraiso-dark.css
│   │       ├── paraiso-light.css
│   │       ├── pastel-on-dark.css
│   │       ├── rubyblue.css
│   │       ├── solarized.css
│   │       ├── the-matrix.css
│   │       ├── tomorrow-night-bright.css
│   │       ├── tomorrow-night-eighties.css
│   │       ├── twilight.css
│   │       ├── vibrant-ink.css
│   │       ├── xq-dark.css
│   │       ├── xq-light.css
│   │       └── zenburn.css
│   ├── flowchart.min.js
│   ├── jquery.flowchart.min.js
│   ├── marked.min.js
│   ├── prettify.min.js
│   ├── raphael.min.js
│   ├── sequence-diagram.min.js
│   └── underscore.min.js
└── plugins
    ├── code-block-dialog
    │   └── code-block-dialog.js
    ├── emoji-dialog
    │   ├── emoji-dialog.js
    │   └── emoji.json
    ├── goto-line-dialog
    │   └── goto-line-dialog.js
    ├── help-dialog
    │   ├── help-dialog.js
    │   └── help.md
    ├── html-entities-dialog
    │   ├── html-entities-dialog.js
    │   └── html-entities.json
    ├── image-dialog
    │   └── image-dialog.js
    ├── link-dialog
    │   └── link-dialog.js
    ├── plugin-template.js
    ├── preformatted-text-dialog
    │   └── preformatted-text-dialog.js
    ├── reference-link-dialog
    │   └── reference-link-dialog.js
    ├── table-dialog
    │   └── table-dialog.js
    └── test-plugin
        └── test-plugin.js

131 directories, 383 files
```
---
 - ## 3.文件引入
 
```html
<link rel="stylesheet" href="/res/editormd/css/editormd.css">
<script src="/res/admin/js/jquery-1.11.2.min.js"></script>
<script src="/res/editormd/editormd.js"></script>
```
---
- ## 4.js 代码

```html
<script type="text/javascript">
    var testEditor;
    testEditor = editormd("test-editormd", {
        width: "100%",
        height: 500,
        path : '/res/editormd/lib/', //自己站点的lib目录
        theme : "gray",
        previewTheme : "dark",
        // editorTheme : "pastel-on-dark",
        markdown  : '',
        codeFold : true,
        //syncScrolling : false,
        saveHTMLToTextarea : true,    // 保存 HTML 到 Textarea
        searchReplace : true,
        watch : false,                // 关闭实时预览
        htmlDecode : "style,script,iframe|on*",            // 开启 HTML 标签解析，为了安全性，默认不开启    
        //toolbar  : false,             //关闭工具栏
        //previewCodeHighlight : false, // 关闭预览 HTML 的代码块高亮，默认开启
        emoji : true,
        taskList : true,
        tocm            : true,         // Using [TOCM]
        tex : true,                   // 开启科学公式TeX语言支持，默认关闭
        flowChart : true,             // 开启流程图支持，默认关闭
        sequenceDiagram : true,       // 开启时序/序列图支持，默认关闭,
        //dialogLockScreen : false,   // 设置弹出层对话框不锁屏，全局通用，默认为true
        //dialogShowMask : false,     // 设置弹出层对话框显示透明遮罩层，全局通用，默认为true
        //dialogDraggable : false,    // 设置弹出层对话框不可拖动，全局通用，默认为true
        //dialogMaskOpacity : 0.4,    // 设置透明遮罩层的透明度，全局通用，默认值为0.1
        //dialogMaskBgColor : "#000", // 设置透明遮罩层的背景颜色，全局通用，默认为#fff
        imageUpload : true,
        imageFormats : ["jpg", "jpeg", "gif", "png", "bmp", "webp"],
        imageUploadURL : "/admin/upload/domdupload",//自己站点的上传方法 也可以用自带的
        onload : function() {
            console.log('onload', this);
        }
    });
</script>
```
---
- ##5.后台php代码
```html
    // 单图上传-editormd
    public function domdupload()
    {
        $file = request()->file('editormd-image-file');
        // $folder = input('param.folder');
        $folder = 'editormd';
        $info = $file->move('./uploads/'.$folder);
        if($info){
            $url=str_replace('\\','/',$info->getSaveName());
            $url='/uploads/'.$folder.'/'.$url;
            $result = ['success'=>1,'url'=>$url,'message'=>'上传成功'];
        }else{
            $result = ['success'=>0,'url'=>'','message'=>$file->getError()];
        }
        echo json_encode($result);
        exit();
    }
```
如果使用自己的上传功能需要 返回json格式的数据
---
- ## 6.编辑editor.md内容 直接添加一个 textarea

```html
<div id="test-editormd"><textarea><?php echo $item['details'];?></textarea></div>
```
