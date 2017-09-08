# [VS Code](https://code.visualstudio.com) Tips and Tricks 官方指南 - 中文翻译版

注：本文由X-hung个人翻译，仅供那些想要使用VSCode但英文却不好或者不想读英文参考的朋友。任何人可自由编辑此文档。版权归Visual Studio Code官方所有。
This Chinese translation version is translated by X-hung, Everybody can edit it if you have better suggestions. Thanks.

# 目录 Table of Contents

1. <a href="#basics">基础 Basics</a>
2. <a href="#customization">个性化 Customization</a>
3. <a href="#extensions">扩展 Extensions</a>
4. <a href="#file-and-folder-management">文件（夹）管理 File and folder management</a>
5. <a href="#editing-hacks">编辑技巧 Editing hacks</a>
6. <a href="#intellisense">智能填充 IntelliSense</a>
7. <a href="#snippets">代码片段 Snippets</a>
8. <a href="#git-integration">Git集成 Git integration</a>
9. <a href="#debugging">调试 Debugging</a>
10. <a href="#task-runner">运行 Task runner</a>
11. <a href="#other-resources">其他资源 Other Resources</a>

> 下文所使用的快捷键可能无法与最新版本精准匹配，点击[这里](https://code.visualstudio.com/docs/getstarted/keybindings)查看最新的快捷键参考.
> The key bindings below may or may not be accurate with the latest build. See [here](https://code.visualstudio.com/docs/getstarted/keybindings) for the latest keyboard shortcut reference.

# 基础 Basics

## VS Code 测试版 Insider Version of VS Code

VS Code团队使用内测版本来测试最新版的功能以及修复Bug。您可以在[这里](https://code.visualstudio.com/insiders)下载相同的测试版
The Visual Studio Code team uses the Insiders version to test the latest features and bug fixes of VS Code. You can use this same version by [downloading here](https://code.visualstudio.com/insiders).

* 对于早期使用者 - 测试版提供最新更改的代码，这将会导致一些偶然的Build失败。
* 高频率Build - 每天都有新的Build，提供最新的Bug修复和新功能。
* 并排安装 - 测试版发布后，稳定版也会随后发布，使您不至于独立的使用两个版本。
* For Early Adopters - Insiders has the most recent code changes and may lead to the occasional broken build.
* Frequent Builds - New builds everyday with the latest bug fixes and features.
* Side-by-side install - Insiders installs next to the Stable build allowing you to use either independently.

![side by side install](/media/side-by-side-install.png)

## 新手上路 Getting Started

打开**欢迎使用**页面开始学习VS Code的基本用法。**帮助** > **欢迎使用**. 
Open the **Welcome** page to get started with the basics of VS Code. **Help** > **Welcome**.

![welcome page](/media/welcome_page.png)

包括**交互式演练场** 
Includes the **Interactive Playground**.

![interactive playground](/media/interactive_playground.png)

## 命令面板 Command Palette

根据您当前打开的内容来获取所有可用命令
Access all available commands based on your current context.

> Mac: <kbd>cmd+shift+p</kbd> or <kbd>f1</kbd>

> Windows / Linux: <kbd>ctrl+shift+p</kbd> or <kbd>f1</kbd>

![command palette](/media/OpenCommandPalatte.gif)

## 快捷键参考 Reference keybindings
所有**命令面板**的命令都能使用与之绑定的快捷键操作（如果存在的话）。如果您忘了要使用哪个快捷键，可以打开**命令面板**找一找。 
All of the commands are in the **Command Palette** with the associated key binding (if it exists). If you forget what the key binding is use the **Command Palette** to help you out.

![keyboard references](/media/keyboard-references.png)

## 快速打开 Quick open

快速打开文件。
Quickly open files.

> Mac: <kbd>cmd+p</kbd>

> Windows / Linux: <kbd>ctrl+p</kbd>

![Quick Open](/media/QuickOpen.gif)

> **提示：** 输入“？”来查看帮助建议。
> **Tip:** Type "?" to view help suggestions.

### 在最近打开的文件中寻找 Navigate between recently opened files
重复使用**快速打开**快捷键在最近打开的文件之间快速循环浏览。
Repeat the **Quick Open** keyboard shortcut to cycle quickly between recently opened files.

### 通过“快速打开”打开多个文件 Open multiple files from Quick Open
您可以使用**快速打开**中的右方向键来快速打开多个文件。这将在后台打开当前选定的文件，此时您可以使用**快速打开**继续选择文件。
You can open multiple files from **Quick Open** by pressing the Right arrow key. This will open the currently selected file in the background and you can continue selecting files from **Quick Open**.

## CLI工具 CLI tool
> Linux系统: 参见[这里](https://code.visualstudio.com/docs/editor/setup#_linux)的说明。
> Linux: Follow instructions [here](https://code.visualstudio.com/docs/editor/setup#_linux).

> Windows系统: 参见[这里](https://code.visualstudio.com/docs/editor/setup#_windows)的说明。
> Windows: Follow instructions [here](https://code.visualstudio.com/docs/editor/setup#_windows).

> Mac系统: 往下看.
> Mac: see below.

打开**命令面板** (<kbd>F1</kbd>) 输入“shell command” 敲击回车键执行 **Shell Command: Install 'code' command in PATH**.
Open the **Command Palette** (<kbd>F1</kbd>) and type "shell command". Hit enter to execute **Shell Command: Install 'code' command in PATH**.

![shell command](/media/setup_shell-command.png)


```bash
# 在当前目录打开代码 open code with current directory
code .

# 在最近使用的代码窗口打开当前目录 open the current directory in the most recently used code window
code -r .

# 新建窗口 create a new window
code -n

# 更改语言 change the language
code --locale=es

# 打开diff编辑器 open diff editor
code --diff <file1> <file2>

# 查看帮助选项 see help options
code --help

# 禁用所有扩展部件 disable all extensions
code --disable-extensions .
```

![all cli commands](/media/vscode-cli-commands.png)

## .vscode文件夹 .vscode folder

工作区的特殊文件都是以`.vscode`为后缀。比如说，`tasks.json` 用来设置运行程序，`launch.json` 用来设置调试程序。
Workspace specific files are in `.vscode`. For example, `tasks.json` for the Task Runner and `launch.json` for the debugger.

## 状态栏修饰 Status Bar decorations

**错误和警告 Errors and Warnings**

> Mac: <kbd>shift+cmd+m</kbd>

> Windows / Linux: <kbd>ctrl+shift+m</kbd>

快速跳转至项目中的错误和警告行。
Quickly jump to errors and warnings in the project.

使用<kbd>f8</kbd> 或者 <kbd>shift+f8</kbd>在错误行中来回浏览。
Cycle through errors with <kbd>f8</kbd> or <kbd>shift+f8</kbd>

![errors and warnings](/media/Errors_Warnings.gif)

您可以输入 ('errors', 'warnings') 或者文本匹配来过滤问题信息。
You can filter problems by type ('errors', 'warnings') or text matching.

**更改语言模式 Change language mode**

> Mac: <kbd>cmd+k m</kbd>

> Windows / Linux: <kbd>ctrl+k m</kbd>

![change syntax](/media/change_syntax.gif)

如果要保留该文件类型的新语言模式，可以使用**关联配置文件...** 命令将当前文件扩展名与已安装语言相关联。
If you want to persist the new language mode for that file type, you can use the **Configure File Association for ...** command to associate the current file extension with an installed language.

# 个性化 Customization

这里有许多方法让您个性化定制VS Code。
There are many things you can do to customize VS Code.

* 更改主题 Change your theme
* 更改键盘快捷键 Change your keyboard shortcuts
* 调整设置 Tune your settings
* 添加JSON验证文件 Add JSON validation
* 创建代码片段 Create snippets
* 安装扩展部件 Install extensions

Check out the full [documentation](https://code.visualstudio.com/docs/getstarted/settings).

## 更改主题 Change your theme

打开**命令面板**输入“主题”，您可以从扩展商店获取更多主题。
Open the **Command Palette** and type "themes". You can install more themes from the extension Marketplace.

![Preview themes](/media/PreviewThemes.gif)

此外，您还可以安装或改变文件图标。
Additionally, you can install and change your File Icon themes.

![File icon themes](/media/PreviewFileIconThemes.gif)

## 更改快捷键 Change your keyboard shortcuts

### 快捷键参考表 Keyboard Reference Sheets

下载适用您的系统的键盘快捷键参考图：([macOS](https://go.microsoft.com/fwlink/?linkid=832143), [Windows](https://go.microsoft.com/fwlink/?linkid=832145), [Linux](https://go.microsoft.com/fwlink/?linkid=832144))。
Download the keyboard shortcut reference sheet for your platform ([macOS](https://go.microsoft.com/fwlink/?linkid=832143), [Windows](https://go.microsoft.com/fwlink/?linkid=832145), [Linux](https://go.microsoft.com/fwlink/?linkid=832144)).

![Keyboard Reference Sheet](/media/KeyboardReferenceSheet.png)

### 键盘布局 Keymaps

您是否习惯了其他编辑器的快捷键方式？在这里您可以安装一个键盘布局扩展来把您喜爱的编辑器的快捷键方式迁移至VS Code。打开**首选项** > **键盘扩展** 查看[扩展商店](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads)里提供的快捷键扩展。
Are you used to keyboard shortcuts from another editor? You can install a Keymap extension that brings the keyboard shortcuts from your favorite editor to VS Code. Go to **Preferences** > **Keymap Extensions** to see the current list on the [Marketplace](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads). 

看一看比较受欢迎的几个：
Some of the more popular ones:

- [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)
- [Sublime Text Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.sublime-keybindings)
- [Emacs Keymap](https://marketplace.visualstudio.com/items?itemName=hiro-sun.vscode-emacs)
- [Atom Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.atom-keybindings)

### 自定义您的快捷键 Customize your keyboard shortcuts

打开**命令面板** 输入“快捷键”。您可以在打开的文件的右侧添加新的快捷键方式。
Open the **Command Palette** and type "keyboard shortcuts." You can now add your own keybindings in the file on the right.

![customize keyboard shortcuts](/media/KeyboardShortcuts.gif)

更多请参见：[Key Bindings for Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings).
See more in [Key Bindings for Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings).

##  调整设置 Tune your settings

打开`settings.json`

Open `settings.json`

> Mac: <kbd>cmd+,</kbd>

> Windows / Linux: **File** > **Preferences** > **Settings**

*粘贴格式 Format on paste*

```json
"editor.formatOnPaste": true
```

*更改字体大小 Change the font size*

```json
"editor.fontSize": 18
```

*更改缩放级别 Change the zoom level*

```json
"window.zoomLevel": 5
```

*英文连字功能 Font ligatures*

```json
"editor.fontFamily": "Fira Code",
"editor.fontLigatures": true
```

> **提示:** 您可能需要安装支持连字功能的字体。 [FiraCode](https://github.com/tonsky/FiraCode) 字体在VS Code团队中是比较受欢迎的。
> **Tip:** You will need to have a font installed that supports font ligatures. [FiraCode](https://github.com/tonsky/FiraCode) is a popular font on the VS Code team.

![font ligatures](/media/font-ligatures-annotated.png)

*自动存档 Auto Save*

```json
"files.autoSave": "afterDelay"
```
您还可以使用顶级菜单中的**文件**> **自动保存**打开自动保存
You can also toggle Auto Save from the top-level menu with the **File** > **Auto Save**.

*保存格式 Format on save*

```json
"editor.formatOnSave": true,
```

*改变缩进字符数 Change the size of tab characters*

```json
"editor.tabSize": 4
```

*缩进改空格 Spaces or tabs*

```json
"editor.insertSpaces": true
```

*空白渲染 Render whitespace*

```json
"editor.renderWhitespace": "all"
```

*忽略文件（夹）Ignore files / folders*

从编辑窗口里删除这些文件（夹）
Removes these files / folders from your editor window.

```json
"files.exclude": {
        "somefolder/": true,
        "somefile": true
}
```
从搜索结果中删除这些文件（夹）
Remove these files / folders from search results.

```json
"search.exclude": {
    "someFolder/": true,
    "somefile": true
}
```

查看[更多](https://code.visualstudio.com/docs/getstarted/settings)。
And many, many [others](https://code.visualstudio.com/docs/getstarted/settings).

## 特定语言设置 Language specific settings

只给一些特定的语言添加设置
For those settings you only want for specific languages.

```json
"[languageid]": {

}
```

> **提示:** 您可以在**命令面板**中输入“更改语言特定设置”来获取语言的ID。
> **Tip:** You can find the language ID by typing in the **Command Palette** "Configure language specific settings"

![language based settings](/media/lang-based-settings.png)

## 添加JASON验证 Add JSON Validation

为大多数文件启用默认设置。您可以在`settings.json`中添加自己的模式和验证
Enabled by default for many files. Create your own schema and validation in `settings.json`

```json
"json.schemas": [
    {
        "fileMatch": [
            "/bower.json"
        ],
        "url": "http://json.schemastore.org/bower"
    }
]
```


或者在您的工作区中定义的模式
or for a schema defined in your workspace

```json
"json.schemas": [
    {
        "fileMatch": [
            "/foo.json"
        ],
        "url": "./myschema.json"
    }
]
```

或者自定义模式
or a custom schema

```json
"json.schemas": [
    {
        "fileMatch": [
            "/.myconfig"
        ],
        "schema": {
            "type": "object",
            "properties": {
                "name" : {
                    "type": "string",
                    "description": "The name of the entry"
                }
            }
        }
    },
```

在[文档](https://code.visualstudio.com/docs/languages/json)中查看更多。
See more in the [documentation](https://code.visualstudio.com/docs/languages/json).

# 扩展部件 Extensions

## 获取扩展部件 Find extensions

1. 在VS Code的[扩展商店](https://marketplace.visualstudio.com/vscode)里查看 In the VS Code [Marketplace](https://marketplace.visualstudio.com/vscode).
2. 在VS Code中直接搜索 Search inside VS Code
3. 查看扩展推荐 View extension recommendations
4. 社区策划的扩展列表，如[awesome-vscode](https://github.com/viatsko/awesome-vscode) Community curated extension lists, such as [awesome-vscode](https://github.com/viatsko/awesome-vscode).

## 安装扩展部件 Install extensions

打开扩展栏，您可以通过搜索框搜索或者点击**更多**（...）按钮来根据安装量过滤或排序扩展部件。
Click the Extensions Activity Bar button. You can search via the search bar or click the **More** (...) button to filter and sort by install count.

![install extensions](/media/InstallExtensions.gif)

## 扩展推荐 Extension recommendations

打开扩展栏，接着在**更多**（...）里点击**推荐**。
Click the Extensions Activity Bar button. Then click **Show Recommended Extensions** in the **More** (...) button menu.

![show recommended extensions](/media/ShowRecommendedExtensions.gif)

## 创建自己的扩展部件 Creating my own extension

您对自建扩展感兴趣吗？您可以在这份文档中学习如何自己创建扩展部件。具体参见[documentation on contribution points](https://code.visualstudio.com/docs/extensionAPI/extension-points)。
Are you interested in creating your own extension? You can learn how to do this in the documentation, specifically check out the [documentation on contribution points](https://code.visualstudio.com/docs/extensionAPI/extension-points).

* 设置 configuration
* 命令 commands
* 快捷键 keybindings
* 语言 languages
* 调试 debuggers
* 语法 grammars
* 主题 themes
* 代码片段 Snippets snippets
* JSON验证 jsonValidation

# 过滤和文件夹管理 File and folder management

## 集成终端 Integrated terminal

> Windows / Linux / Mac: <kbd>ctrl+`</kbd>

![Integrated terminal](/media/integrated_terminal.png)

查看更多：
Further reading:

- [Official documentation](https://code.visualstudio.com/docs/editor/integrated-terminal)
- [Mastering VS Code's Terminal article](http://www.growingwiththeweb.com/2017/03/mastering-vscodes-terminal.html)


## 自动存档 Auto Save

使用 <kbd>cmd+,</kbd> 打开 `settings.json`

Open `settings.json` with <kbd>cmd+,</kbd>

```json
"files.autoSave": "afterDelay"
```
您还可以使用顶级菜单中的**文件**> **自动保存**打开自动保存
You can also toggle Auto Save from the top-level menu with the **File** > **Auto Save**.

## 打开侧边栏 Toggle Sidebar

> Mac: <kbd>cmd+b</kbd>

> Windows / Linux: <kbd>ctrl+b</kbd>

![toggle side bar](/media/toggle_side_bar.gif)

## 禅模式 Zen Mode

> Mac: <kbd>cmd+k z</kbd>

> Windows / Linux: <kbd>ctrl+k z</kbd>

![zen mode](/media/zen_mode.gif)

进入不会让您分心的禅模式。
Enter distraction free Zen mode.

## 并排编辑 Side by side editing

> Mac: <kbd>cmd+\\</kbd> or <kbd>cmd</kbd> then click a file from the File Explorer.

> Windows / Linux: <kbd>ctrl+\\</kbd>

> Linux: <kbd>ctrl+2</kbd>

![split editors](/media/split_editor.gif)

您可以拖放编辑器来创建新的编辑器组并且在组与组之间移动编辑器。
You can use drag and drop editors to create new editor groups and move editors between groups.

## 在编辑器之间切换 Switch between editors

> Mac: <kbd>cmd+1</kbd>, <kbd>cmd+2</kbd>, <kbd>cmd+3</kbd>

> Windows / Linux: <kbd>ctrl+1</kbd>, <kbd>ctrl+2</kbd>, <kbd>ctrl+3</kbd>

![navigate editors](/media/navigate_editors.gif)

## 移动至探索窗口 Move to Explorer window

> Mac: <kbd>cmd+shift+e</kbd>

> Windows / Linux: <kbd>ctrl+shift+e</kbd>

## 新建&打开文件 Create and open a file

> Mac: <kbd>cmd+click</kbd>

> Windows / Linux: <kbd>ctrl+click</kbd>

![create and open file](/media/create_open_file.gif)

## 关闭当前文件夹 Close the currently opened folder

> Mac: <kbd>cmd+w</kbd>

> Windows / Linux: <kbd>ctrl+k f</kbd>

## 历史纪录 History

使用<kbd>ctrl+tab</kbd>浏览全部历史纪录
Navigate entire history with <kbd>ctrl+tab</kbd>

向下浏览
Navigate back.

> Mac: <kbd>ctrl+-</kbd>

> Windows / Linux: <kbd>alt+left</kbd>

向上浏览
Navigate Forward.

> Mac: <kbd>ctrl+shift+-</kbd>

> Windows / Linux: <kbd>alt+right</kbd>

![navigate history](/media/navigate_history.gif)

## 转至某文件 Navigate to a file

> Mac: <kbd>cmd+e</kbd> or <kbd>cmd+p</kbd>

> Windows / Linux: <kbd>ctrl+e</kbd> or <kbd>ctrl+p</kbd>

![navigate to file](/media/navigate_to_file.gif)

## 文件关联 File associations

为没有准确检测到的文件创建语言关联（例如，许多配置文件是JSON格式）。
Create language associations for files that aren't detected accurately (for example, many config files are JSON).

```json
"file.associations": {
    ".database": "json"
}
```

# 编辑技巧 Editing hacks

以下是常见编辑代码的功能选择。如果您觉得这些组合快捷键用得不舒服，可以考虑安装一个[Keymap extension](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads)。
Here are a selection of common features for editing code. If the keyboard shortcuts aren't comfortable for you, consider installing a [Keymap extension](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads) for your old editor.

## 多光标选择 Multi cursor selection

> Mac: <kbd>opt+cmd+up</kbd> or <kbd>opt+cmd+down</kbd>

> Windows: <kbd>ctrl+alt+up</kbd> or <kbd>ctrl+alt+down</kbd>

> Linux: <kbd>alt+shift+up</kbd> or <kbd>alt+shift+down</kbd>

![multi cursor](/media/multi_cursor.gif)

![multi cursor second example](/media/editingevolved_multicursor.gif)

在当前的选择上添加更多光标
Add more cursors to current selection.

![add cursor to all occurrences of current selection](/media/add_cursor_current_selection.gif)

## 多行转单行 Join line

> Mac: <kbd>ctrl+j</kbd>

> Windows / Linux: 默认没有绑定快捷键。 打开键盘快捷方式设置，在`editor.action.joinLines` 中绑定一个您自己的快捷键设置。
> Windows / Linux: Not bound by default. Open Keyboard Shortcuts and bind `editor.action.joinLines` to a shortcut of your choice.

![Join lines](/media/JoinLines.gif)

## 复制上/下一行的内容 Copy line up / down

> Mac: <kbd>opt+shift+up</kbd> or <kbd>opt+shift+down</kbd>

> Windows / Linux([Issue #5363](https://github.com/Microsoft/vscode/issues/5363)): <kbd>shift+alt+down</kbd> or <kbd>shift+alt+up</kbd>

![copy line down](/media/copy_line_down.gif)

## 扩大/减少选择区 Shrink / expand selection

更多参见[documentation](https://code.visualstudio.com/docs/editor/editingevolved#_selection-multicursor)
More in [documentation](https://code.visualstudio.com/docs/editor/editingevolved#_selection-multicursor)

> Mac: <kbd>ctrl+shift+cmd+left</kbd> or <kbd>ctrl+shift+cmd+right</kbd>

> Windows / Linux: <kbd>shift+alt+left</kbd> or <kbd>shift+alt+right</kbd>

![shrink expand selection](/media/shrink_expand_selection.gif)

## 转到文件中的符号 Go to Symbol in File

> Mac: <kbd>cmd+shift+o</kbd>

> Windows / Linux: <kbd>ctrl+shift+o</kbd>

![Find by symbol](/media/find_by_symbol.gif)

您可以通过添加冒号`@:`来分类符号。
You can group the symbols by kind by adding a colon, `@:`.

![group symbols by kind](/media/group_symbols_by_kind.png)

## 转到工作区中的符号 Go to Symbol in Workspace

> Mac: <kbd>cmd+t</kbd>

> Windows / Linux: <kbd>ctrl+t</kbd>

![go to symbol in workspace](/media/go_to_symbol_in_workspace.png)

## 转至特定行 Navigate to a specific line

> Mac: <kbd>ctrl+g</kbd> or <kbd>cmd+p, :</kbd>

> Windows / Linux: <kbd>ctrl+g</kbd>

![navigate to line](/media/navigate_to_line.gif)

## 撤销光标位 Undo cursor position

> Mac: <kbd>cmd+u</kbd>

> Windows / Linux: <kbd>ctrl+u</kbd>

![undo cursor position](/media/undo_cursor_position.gif)

## 向上/下移动该行 Move line up and down

> Mac: <kbd>opt+up</kbd> or <kbd>opt+down</kbd>

> Windows / Linux: <kbd>alt+up</kbd> or <kbd>alt+down</kbd>

![move line up and down](/media/move_line.gif)

## 删除行尾空格 Trim trailing whitespace

> Mac: <kbd>cmd+k cmd+x</kbd>

> Windows / Linux: <kbd>ctrl+k</kbd> <kbd>ctrl+x</kbd>

![trailing whitespace](/media/trim_whitespace.gif)

## 代码格式 Code formatting

### 当前选择的源代码格式 Currently selected source code

> Mac: <kbd>cmd+k, cmd+f</kbd>

> Windows / Linux: <kbd>ctrl+k, ctrl+f</kbd>

### 所有文档格式 Whole document format

> Windows / Linux: <kbd>shift+alt+f</kbd>

![code formatting](/media/code_formatting.gif)

## 代码折叠 Code folding

> Mac: <kbd>shift+cmd+\[</kbd> and <kbd>shift+cmd+\]</kbd>

> Windows / Linux: <kbd>ctrl+shift+\[</kbd> and <kbd>ctrl+shift+\]</kbd>

![code folding](/media/code_folding.gif)

## 选择当前行 Select current line

> Mac: <kbd>cmd+i</kbd>

> Windows / Linux: <kbd>ctrl+i</kbd>

![select current line](/media/select_current_line.gif)

## 转至文件顶部/尾部 Navigate to beginning and end of file

> Mac: <kbd>cmd+up</kbd> and <kbd>cmd+down</kbd>

> Windows: <kbd>ctrl+up</kbd> and <kbd>ctrl+down</kbd>

> Linux: <kbd>ctrl+home</kbd> and <kbd>ctrl+end</kbd>

![navigate to beginning and end of file](/media/beginning_end_file.gif)

## 打开Markdown预览界面 Open Markdown Preview

在Markdown文件中，使用
In a Markdown file, use

> Mac: <kbd>shift+cmd+v</kbd>

> Windows / Linux: <kbd>ctrl+shift+v</kbd>

![toggle readme preview](/media/toggle_preview.gif)

## 并排显示Markdown编辑和预览 Side by Side Markdown Edit and Preview

在Markdown文件中，使用
In a Markdown file, use

> Mac: <kbd>cmd+k v</kbd>

> Windows / Linux: <kbd>ctrl+k v</kbd>

彩蛋：预览此时会同步进行
Special bonus: The preview will now sync.

![markdown sync](/media/markdown-preview-sync.gif)

# 智能填充 IntelliSense

在任何时候，使用<kbd>ctrl+space</kbd>来触发建议插件
Anytime, try <kbd>ctrl+space</kbd> to trigger the Suggestions widget.

![intellisense](/media/intellisense.gif)

您可以查看可用的方法，参数提示，短文档等。
You can view available methods, parameter hints, short documentation, etc.

## Peek

选择一个符号，接着按下<kbd>alt+f12</kbd>。或者，您可以使用上下文菜单。
Select a symbol then type <kbd>alt+f12</kbd>. Alternatively, you can use the context menu.

![peek](/media/peek.gif)

## 转至定义 Go to Definition

选择一个符号，接着按下<kbd>f12</kbd>。或者，您可以使用上下文菜单。
Select a symbol then type <kbd>f12</kbd>. Alternatively, you can use the context menu or <kbd>ctrl+click</kbd> (<kbd>cmd+click</kbd> on macOS).

![go to definition](/media/goto_definition.gif)

您可以使用**转到** > **后退** 命令或者 <kbd>alt+left</kbd> (Mac OS中使用 <kbd>ctrl+-</kbd> )返回到之前的位置。
You can go back to your previous location with the **Go** > **Back** command or <kbd>alt+left</kbd> (<kbd>ctrl+-</kbd> on macOS).

## 查找所有的参考 Find All References

选择一个符号，接着按下<kbd>shift+f12</kbd>。或者，您可以使用上下文菜单。
Select a symbol then type <kbd>shift+f12</kbd>. Alternatively, you can use the context menu.

![find all references](/media/find_all_references.gif)

## 重命名符号 Rename Symbol

选择一个符号，接着按下<kbd>f2</kbd>。或者，您可以使用上下文菜单。
Select a symbol then type <kbd>f2</kbd>. Alternatively, you can use the context menu.

![rename symbol](/media/rename_symbol.gif)

## .eslintrc.json

安装[ESLint 扩展](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)，按照您喜欢的方式设置。详见[这里](http://eslint.org/docs/user-guide/configuring)。
Install the [ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint). Configure
your linter however you'd like. Specification is [here](http://eslint.org/docs/user-guide/configuring).

下面是使用ES6的配置
Here is configuration to use ES6.

```json
{
    "env": {
        "browser": true,
        "commonjs": true,
        "es6": true,
        "node": true
    },
    "parserOptions": {
        "ecmaVersion": 6,
        "sourceType": "module",
        "ecmaFeatures": {
            "jsx": true,
            "classes": true,
            "defaultParams": true
        }
    },
    "rules": {
        "no-const-assign": 1,
        "no-extra-semi": 0,
        "semi": 0,
        "no-fallthrough": 0,
        "no-empty": 0,
        "no-mixed-spaces-and-tabs": 0,
        "no-redeclare": 0,
        "no-this-before-super": 1,
        "no-undef": 1,
        "no-unreachable": 1,
        "no-use-before-define": 0,
        "constructor-super": 1,
        "curly": 0,
        "eqeqeq": 0,
        "func-names": 0,
        "valid-typeof": 1
    }
}
```

## package.json

在`package.json`文件中查看智能填充设置
See IntelliSense for your `package.json` file.

![package json intellisense](/media/package_json_intellisense.gif)

## 缩写语法 Emmet syntax

[Support for Emmet syntax](https://code.visualstudio.com/docs/languages/html#_emmet-snippets).

![emmet syntax](/media/emmet_syntax.gif)

# 代码片段 Snippets

## 创建自定义代码片段 Create custom snippets

**文件** > **首选项** > **用户代码片段**，选择一种语言并创建新的代码片段

**File** > **Preferences** > **User Snippets**, select the language, and create a snippet.

```json
"create component": {
    "prefix": "component",
    "body": [
        "class $1 extends React.Component {",
        "",
        "	render() {",
        "		return ($2);",
        " 	}",
        "",
        "}"
    ]
},
```

详情参见[Creating your own Snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets)。
See more details in [Creating your own Snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets).

# Git集成 Git Integration

Git集成带有VS Code中的“in-the-box”。您可以从扩展商店中安装其他SCM提供程序。本节仅介绍Git集成。其他的SCM提供了更多的UI和手势。
Git integration comes with VS Code "in-the-box". You can install other SCM provider from the extension Marketplace. This section describes the Git integration but much of the UI and gestures are shared by other SCM providers.

## Diffs

点击侧边栏的**源代码管理**按钮，接着选择文件来diff。
Click the Source Control button in the Activity Bar then select the file to diff.

![git icon](/media/git_icon.png)

**并排窗口 Side by side**

默认的是并排Diff。
Default is side by side diff.

![git diff side by side](/media/git_side_by_side.png)

**在行内查看 Inline view**

在窗口顶部右侧点击**更多（...）** > **切换为行内查看**切换至行内查看模式
Toggle inline view by clicking the **More** (...) button in the top right and selecting **Switch to Inline View**.

![more git button](/media/more_button.png)

![git inline](/media/git_inline.png)

如果您偏好行内查看，可以设置`"diffEditor.renderSideBySide": false`。
If you prefer the inline view, you can set `"diffEditor.renderSideBySide": false`.


**审查窗格 Review Pane**

按`F7` 和 `Shift+F7`在diff中导航。这将以统一的补丁格式呈现。使用方向键在行与行之间转换，按下 `Enter` 键会跳转回diff编辑器并定位到选择的行。
Navigate through diffs with `F7` and `Shift+F7`. This will present them in a unified patch format. 
Lines can be navigated with arrow keys and pressing `Enter` will jump back in the diff editor and the selected line.

![diff_review_pane](/media/diff_review_pane.png)


**编辑待更改的文件 Edit pending changes**

您可以在diff模式下直接编辑待更改的文件。
You can make edits directly in the pending changes of the diff view.


## 分支 Branches

通过底部状态栏的按钮轻松地切换Git分支。
Easily switch between Git branches via the Status Bar.

![switch branches](/media/switch_branches.gif)

## 选择 Staging

**选择全部 Stage all**

将鼠标悬停在文件编号上，然后单击加号按钮。
Hover over the number of files and click the plus button.

![git stage all](/media/git_stage_all.gif)

**选择部分 Stage selected**

选择该文件（使用方向键），然后从**命令面板**中选择**Stage Selected Range（部分选择范围）**来选择文件的一部分。
Stage a portion of a file by selecting that file (using the arrows) and then choosing **Stage Selected Ranges** from the **Command Palette**.

![git stage selected](https://cloud.githubusercontent.com/assets/1926584/23407797/ebeefbb4-fdc5-11e6-8ca1-c4c6c056a8fd.png)

## 撤销前一次提交 Undo last commit

![undo last commit](/media/undo_last_commit.gif)

## 查看Git输出 See Git output

在VS Code中可以轻松地查看Git实际正在运行的每一条指令。这对正在学习Git或者Debug一个不同源的问题很有用。
VS Code makes it easy to see what Git commands are actually running. This is helpful when learning Git or debugging a difficult source control issue.

> Mac: <kbd>shift+cmd+u</kbd>

> Windows / Linux: <kbd>ctrl+shift+u</kbd>

运行`toggleOutput`. 在下拉菜单中选择**Git**
to run `toggleOutput`. Select **Git** in the drop-down.

## Gutter指示器 Gutter indicators

查看编辑器中的diff修饰。详情参见该[文档](https://code.visualstudio.com/docs/editor/versioncontrol#_gutter-indicators)
View diff decorations in editor. See [documentation](https://code.visualstudio.com/docs/editor/versioncontrol#_gutter-indicators) for more details.

![git gutter indicators](/media/editingevolved_gutter.png)

## 解决合并冲突 Resolve merge conflicts

在合并时，点击侧边栏的**源代码管理**按钮，在Diff模式下更改。
During a merge, click the Source Control button in the Activity Bar and make changes in the diff view.

![git icon](/media/git_icon.png)

## 设置VS Code为默认合并工具 Setup VS Code as default merge tool

```bash
git config --global merge.tool code
```

# 调试 Debugging

## 设置调试器 Configure debugger

<kbd>f1</kbd> and select **Debug: Open launch.json**, select the environment. This will generate a `launch.json` file. Works out of the box as expected for Node.js and other environments. May need some additional configuration for other languages. See [documentation](https://code.visualstudio.com/docs/editor/debugging) for more details.

![configure debugging](/media/configure_debug.gif)

## 断点和按步运行 Breakpoints and stepping through

在行号旁边放置断点， 使用“调试”窗口小部件向下导航。
Place breakpoints next to the line number. Navigate forward with the Debug widget.

![debug](/media/node_debug.gif)

## 数据检查 Data inspection

在**控制台**中的**调试控制台**面板查看数据检查。
Inspect variables in the Debug panels and in the console.

![data inspection](/media/debug_data_inspection.gif)

## 行内查看 Inline values

您可以设置`"debug.inlineValues": true`来在调试器的行内查看变量值。这是一个试验功能，默认是关闭的。
You can set `"debug.inlineValues": true` to see variable values inline in the debugger. This feature is experimental and disabled by default.

# 任务运行 Task Runner

## 自动检测任务 Auto detect tasks

选择顶部菜单栏中的**任务** > **配置任务...**，接着选择您想要运行的任务类型。此操作会生成一个名为`task.json` 的配置文件，就像下面显示的内容一样。更多内容参见[此文档](https://go.microsoft.com/fwlink/?LinkId=733558)。

Select **Tasks** from the top-level menu, run the command **Configure Tasks...**, then select the type of task you'd like to run.
This will generate a `task.json` file with content like the following. See the Tasks [documentation](https://go.microsoft.com/fwlink/?LinkId=733558) for more details.

```json
{
    // See http://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "0.1.0",
    "command": "npm",
    "isShellCommand": true,
    "showOutput": "always",
    "suppressTaskName": true,
    "tasks": [
        {
            "taskName": "install",
            "args": ["install"]
        },
        {
            "taskName": "build",
            "args": ["run", "build"]
        }
    ]
}
```
此处偶尔会出现有关自动生成的问题。查看文档来获取合适的方法。
There are occasionally issues with auto generation. Check out the documentation for getting things to work properly.

## 从任务菜单运行任务 Run tasks from the Tasks menu

从顶部菜单栏选择**任务** > **运行任务...**，接着选择您想要运行的任务。此外还可以使用**终止任务...** 选项来终止任务的运行。
Select **Tasks** from the top-level menu, run the command **Run Task...**, and select the task you want to run. Terminate the running task by running the command **Terminate Task...**

![task runner](/media/task_runner.gif)


## 其他资源 Other Resources

* [vscode official docs](https://code.visualstudio.com/docs)
* [react sample app](https://github.com/Microsoft/vscode-react-sample)
* [awesome vscode](https://github.com/viatsko/awesome-vscode)
