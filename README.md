# [VS Code](https://code.visualstudio.com) Tips and Tricks

>**Note**: Tips and Tricks has moved to the official Visual Studio Code documentation at [code.visualstudio.com](https://code.visualstudio.com/docs/getstarted/tips-and-tricks).<BR>
>The content is now at [vscode-docs](https://github.com/Microsoft/vscode-docs/blob/master/docs/getstarted/tips-and-tricks.md). Pull requests and documentation issues are still greatly appreciated.

# Table of Contents

1. <a href="#basics">Basics</a>
2. <a href="#customization">Customization</a>
3. <a href="#extensions">Extensions</a>
4. <a href="#file-and-folder-management">File and Folder Management</a>
5. <a href="#editing-hacks">Editing Hacks</a>
6. <a href="#intellisense">IntelliSense</a>
7. <a href="#snippets">Snippets</a>
8. <a href="#git-integration">Git Integration</a>
9. <a href="#debugging">Debugging</a>
10. <a href="#task-runner">Task Runner</a>
11. <a href="#other-resources">Other Resources</a>

> The key bindings below may or may not be accurate with the latest build. See [here](https://code.visualstudio.com/docs/getstarted/keybindings) for the latest keyboard shortcut references.

# Basics

## Insider Version of VS Code

The Visual Studio Code team uses the Insiders version to test the latest features and bug fixes of VS Code. You can use this same version by [downloading here](https://code.visualstudio.com/insiders).

* For Early Adopters - Insiders has the most recent code changes and may lead to the occasional broken build.
* Frequent Builds - New builds everyday with the latest bug fixes and features.
* Side-by-side Install - Insiders installs next to the Stable build allowing you to use either independently.

![Side-by-side Install](/media/side-by-side-install.png)

## Getting Started

Open the **Welcome** page to get started with the basics of VS Code. **Help** > **Welcome**.

![Welcome Page](/media/welcome_page.png)

Includes the **Interactive Playground**.

![Interactive Playground](/media/interactive_playground.png)

## Command Palette

Access all available commands based on your current context.

> Mac: <kbd>Cmd+Shift+P</kbd> or <kbd>F1</kbd>

> Windows / Linux: <kbd>Ctrl+Shift+P</kbd> or <kbd>F1</kbd>

![Command Palette](/media/OpenCommandPalatte.gif)

## Reference Keybindings

All of the commands are in the **Command Palette** with the associated key binding (if it exists). If you forget what the key binding is, use the **Command Palette** to help you out.

![Keyboard References](/media/keyboard-references.png)

## Quick Open

Quickly open files.

> Mac: <kbd>Cmd+P</kbd>

> Windows / Linux: <kbd>Ctrl+P</kbd>

![Quick Open](/media/QuickOpen.gif)

> **Tip:** Type "?" to view helpful suggestions.

### Navigate between recently opened files

Repeat the **Quick Open** keyboard shortcut to cycle quickly between recently opened files.

### Open multiple files from Quick Open

You can open multiple files from **Quick Open** by pressing the Right Arrow key. This will open the currently selected file in the background and you can continue selecting files from **Quick Open**.

## CLI tool

> Linux: Follow instructions [here](https://code.visualstudio.com/docs/setup/linux).

> Windows: Follow instructions [here](https://code.visualstudio.com/docs/setup/windows).

> Mac: see below.

Open the **Command Palette** (<kbd>F1</kbd>) and type "shell command". Hit enter to execute **Shell Command: Install 'code' command in PATH**.

![Shell Command](/media/setup_shell-command.png)


```bash
# open code with current directory
code .

# open the current directory in the most recently used code window
code -r .

# create a new window
code -n

# change the language
code --locale=es

# open diff editor
code --diff <file1> <file2>

# see help options
code --help

# disable all extensions
code --disable-extensions .
```

![All CLI Commands](/media/vscode-cli-commands.png)

## .vscode folder

Workspace specific files are in `.vscode`. For example, `tasks.json` for the Task Runner and `launch.json` for the Debugger.

## Status Bar Decorations

**Errors and Warnings**

> Mac: <kbd>Cmd+Shift+M</kbd>

> Windows / Linux: <kbd>Ctrl+Shift+M</kbd>

Quickly jump to errors and warnings in the project.

Cycle through errors with <kbd>F8</kbd> or <kbd>Shift+F8</kbd>

![Errors and Warnings](/media/Errors_Warnings.gif)

You can filter problems by type ('errors', 'warnings') or text matching.

**Change Language Mode**

> Mac: <kbd>Cmd+K M</kbd>

> Windows / Linux: <kbd>Ctrl+K M</kbd>

![Change Syntax](/media/change_syntax.gif)

If you want to persist the new language mode for that file type, you can use the **Configure File Association for ...** command to associate the current file extension with an installed language.

# Customization

There are many things you can do to customize VS Code.

* Change your Theme
* Change your Keyboard Shortcuts
* Tune your Settings
* Add JSON Validation
* Create Snippets
* Install Extensions

Check out the full [documentation](https://code.visualstudio.com/docs/getstarted/settings).

## Change your Theme

Open the **Command Palette** and type "themes". You can install more themes from the Marketplace.

![Preview themes](/media/PreviewThemes.gif)

Additionally, you can install and change your File Icon themes.

![File Icon themes](/media/PreviewFileIconThemes.gif)

## Change your Keyboard Shortcuts

### Keyboard Reference Sheets

Download the keyboard Shortcut Reference Sheet for your platform ([macOS](https://go.microsoft.com/fwlink/?linkid=832143), [Windows](https://go.microsoft.com/fwlink/?linkid=832145), [Linux](https://go.microsoft.com/fwlink/?linkid=832144)).

![Keyboard Reference Sheet](/media/KeyboardReferenceSheet.png)

### Keymaps

Are you used to keyboard shortcuts from another editor? You can install a Keymap extension that brings the keyboard shortcuts from your favorite editor to VS Code. Go to **Preferences** > **Keymap Extensions** to see the current list on the [Marketplace](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads). Some of the more popular ones:

- [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)
- [Sublime Text Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.sublime-keybindings)
- [Emacs Keymap](https://marketplace.visualstudio.com/items?itemName=hiro-sun.vscode-emacs)
- [Atom Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.atom-keybindings)
- [Eclipse Keymap](https://marketplace.visualstudio.com/items?itemName=alphabotsec.vscode-eclipse-keybindings)

### Customize your Keyboard Shortcuts

Open the **Command Palette** and type "keyboard shortcuts". You can now add your own keybindings in the file on the right.

![Customize keyboard shortcuts](/media/KeyboardShortcuts.gif)

See more in [Key Bindings for Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings).

## Tune your Settings

Open `settings.json`

> Mac: <kbd>Cmd + ,</kbd>

> Windows / Linux: **File** > **Preferences** > **Settings** or <kbd>Ctrl + ,</kbd>

*Format on paste*

```json
"editor.formatOnPaste": true
```

*Change the font size*

```json
"editor.fontSize": 18
```

*Change the zoom level*

```json
"window.zoomLevel": 5
```

*Font ligatures*

```json
"editor.fontFamily": "Fira Code",
"editor.fontLigatures": true
```

> **Tip:** You will need to have a font installed that supports font ligatures. [FiraCode](https://github.com/tonsky/FiraCode) is a popular font on the VS Code team.

![Font ligatures](/media/font-ligatures-annotated.png)

*Auto Save*

```json
"files.autoSave": "afterDelay"
```

You can also toggle Auto Save from the top-level menu with the **File** > **Auto Save**.

*Format on save*

```json
"editor.formatOnSave": true,
```

*Change the size of tab characters*

```json
"editor.tabSize": 4
```

*Spaces or tabs*

```json
"editor.insertSpaces": true
```

*Render whitespace*

```json
"editor.renderWhitespace": "all"
```

*Ignore files / folders*

Removes these files / folders from your editor window.

```json
"files.exclude": {
        "somefolder/": true,
        "somefile": true
}
```

Remove these files / folders from search results.

```json
"search.exclude": {
    "someFolder/": true,
    "somefile": true
}
```

And many, many [others](https://code.visualstudio.com/docs/getstarted/settings).

## Language Specific Settings

For those settings you only want for specific languages.

```json
"[languageid]": {

}
```

> **Tip:** You can find the language ID by typing in the **Command Palette** "Configure language specific settings"

![language based settings](/media/lang-based-settings.png)

## Add JSON Validation

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

See more in the [documentation](https://code.visualstudio.com/docs/languages/json).

# Extensions

## Find Extensions

In the VS Code [Marketplace](https://marketplace.visualstudio.com/vscode), you can search for extensions or view extension recommendations or get community curated extension lists, such as [awesome-vscode](https://github.com/viatsko/awesome-vscode).

## Install Extensions

Click the Extensions Activity Bar button. You can search via the Search Bar or click the **More** (...) button to filter and sort by install count.

![Install extensions](/media/InstallExtensions.gif)

## Extension Recommendations

Click the Extensions Activity Bar button. Then click **Show Recommended Extensions** in the **More** (...) button menu.

![Show recommended extensions](/media/ShowRecommendedExtensions.gif)

## Creating my own Extension

Are you interested in creating your own extension? You can learn how to do this in the documentation, specifically check out the [documentation on contribution points](https://code.visualstudio.com/docs/extensionAPI/extension-points). A simple "Hello, world" tutorial can be found [here](https://code.visualstudio.com/docs/extensions/example-hello-world).

# File and Folder Management

## Integrated Terminal

> Windows / Linux / Mac: <kbd>Ctrl + `</kbd>

![Integrated terminal](/media/integrated_terminal.png)

Further reading:

- [Official Documentation](https://code.visualstudio.com/docs/editor/integrated-terminal)
- [Mastering VS Code's Terminal article](http://www.growingwiththeweb.com/2017/03/mastering-vscodes-terminal.html)


## Auto Save

Open `settings.json` with <kbd>Cmd + ,</kbd> for Mac and <kbd>Ctrl + ,</kbd> for Windows / Linux 

```json
"files.autoSave": "afterDelay"
```

You can also toggle Auto Save from the top-level menu with the **File** > **Auto Save**.

## Toggle Sidebar

> Mac: <kbd>Cmd+B</kbd>

> Windows / Linux: <kbd>Ctrl+B</kbd>

![Toggle side bar](/media/toggle_side_bar.gif)

## Zen Mode

> Mac: <kbd>Cmd+K Z</kbd>

> Windows / Linux: <kbd>Ctrl+K Z</kbd>

![Zen mode](/media/zen_mode.gif)

Enter distraction free Zen mode.

## Side by side Editing

> Mac: <kbd>Cmd + \\</kbd> or <kbd>Cmd</kbd> then click a file from the File Explorer.

> Windows / Linux: <kbd>Ctrl + \\</kbd>

> Linux: <kbd>Ctrl+2</kbd>

![Split editors](/media/split_editor.gif)

You can use drag and drop editors to create new editor groups and move editors between groups.

## Switch between Editors

> Mac: <kbd>Cmd+1</kbd>, <kbd>Cmd+2</kbd>, <kbd>Cmd+3</kbd>

> Windows / Linux: <kbd>Ctrl+1</kbd>, <kbd>Ctrl+2</kbd>, <kbd>Ctrl+3</kbd>

![Navigate editors](/media/navigate_editors.gif)

## Move to Explorer Window

> Mac: <kbd>Cmd+Shift+E</kbd>

> Windows / Linux: <kbd>Ctrl+Shift+E</kbd>

## Create and open a file

> Mac: <kbd>Cmd+Click</kbd>

> Windows / Linux: <kbd>Ctrl+Click</kbd>

![Create and open file](/media/create_open_file.gif)

## Close the Currently Opened Folder

> Mac: <kbd>Cmd+W</kbd>

> Windows / Linux: <kbd>Ctrl+K F</kbd>

## History

Navigate entire history with <kbd>Ctrl+Tab</kbd>

Navigate back.

> Mac: <kbd>Ctrl+-</kbd>

> Windows / Linux: <kbd>Alt+&#x2190;</kbd>

Navigate Forward.

> Mac: <kbd>Ctrl+Shift+-</kbd>

> Windows / Linux: <kbd>Alt+&#x2192;</kbd>

![Navigate history](/media/navigate_history.gif)

## Navigate to a File

> Mac: <kbd>Cmd+E</kbd> or <kbd>Cmd+P</kbd>

> Windows / Linux: <kbd>Ctrl+E</kbd> or <kbd>Ctrl+P</kbd>

![Navigate to file](/media/navigate_to_file.gif)

## File Associations

Create language associations for files that aren't detected accurately (for example, many config files are JSON).

```json
"file.associations": {
    ".database": "json"
}
```

# Editing Hacks

Here are a selection of common features for editing code. If the keyboard shortcuts aren't comfortable for you, consider installing a [Keymap extension](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads) for your old editor.

## Multi Cursor Selection

> Mac: <kbd>Cmd+Opt+&#x2191;</kbd> or <kbd>Cmd+Opt+&#x2193;</kbd>

> Windows: <kbd>Ctrl+Alt+&#x2191;</kbd> or <kbd>Ctrl+Alt+&#x2193;</kbd>

> Linux: <kbd>Shift+Alt+&#x2191;</kbd> or <kbd>Shift+Alt+&#x2193;</kbd>

![Multi cursor](/media/multi_cursor.gif)

![Multi cursor second example](/media/editingevolved_multicursor.gif)

Add more cursors to current selection.

![Add cursor to all occurrences of current selection](/media/add_cursor_current_selection.gif)

## Join Line

> Mac: <kbd>Ctrl+J</kbd>

> Windows / Linux: Not bound by default. Open Keyboard Shortcuts and bind `editor.action.joinLines` to a shortcut of your choice.

![Join lines](/media/JoinLines.gif)

## Copy Line Up / Down

> Mac: <kbd>Opt+Shift+&#x2191;</kbd> or <kbd>Opt+Shift+&#x2193;</kbd>

> Windows / Linux([Issue #5363](https://github.com/Microsoft/vscode/issues/5363)): <kbd>Shift+Alt+&#x2191;</kbd> or <kbd>Shift+Alt+&#x2193;</kbd>

![Copy line down](/media/copy_line_down.gif)

## Shrink / Expand Selection

More in [documentation](https://code.visualstudio.com/docs/editor/editingevolved#_selection-multicursor)

> Mac: <kbd>Ctrl+Shift+Cmd+Left</kbd> or <kbd>Ctrl+Shift+Cmd+Right</kbd>

> Windows / Linux: <kbd>Shift+Alt+Left</kbd> or <kbd>Shift+Alt+Right</kbd>

![Shrink expand selection](/media/shrink_expand_selection.gif)

## Go to Symbol in File

> Mac: <kbd>Cmd+Shift+O</kbd>

> Windows / Linux: <kbd>Ctrl+Shift+O</kbd>

![Find by symbol](/media/find_by_symbol.gif)

You can group the symbols by kind by adding a colon, `@:`.

![Group symbols by kind](/media/group_symbols_by_kind.png)

## Go to Symbol in Workspace

> Mac: <kbd>Cmd+T</kbd>

> Windows / Linux: <kbd>Ctrl+T</kbd>

![Go to symbol in workspace](/media/go_to_symbol_in_workspace.png)

## Navigate to a Specific Line

> Mac: <kbd>Ctrl+G</kbd> or <kbd>Cmd+P :</kbd>

> Windows / Linux: <kbd>Ctrl+G</kbd>

![Navigate to line](/media/navigate_to_line.gif)

## Undo Cursor Position

> Mac: <kbd>Cmd+U</kbd>

> Windows / Linux: <kbd>Ctrl+U</kbd>

![Undo cursor position](/media/undo_cursor_position.gif)

## Move Line Up and Down

> Mac: <kbd>Opt+&#x2191;</kbd> or <kbd>opt+&#x2193;</kbd>

> Windows / Linux: <kbd>Alt+&#x2191;</kbd> or <kbd>Alt+&#x2193;</kbd>

![Move line up and down](/media/move_line.gif)

## Trim Trailing Whitespace

> Mac: <kbd>Cmd+K Cmd+X</kbd>

> Windows / Linux: <kbd>Ctrl+K Ctrl+X</kbd>

![Trailing whitespace](/media/trim_whitespace.gif)

## Code Formatting

### Currently Selected Source Code

> Mac: <kbd>Cmd+K Cmd+F</kbd>

> Windows / Linux: <kbd>Ctrl+K Ctrl+F</kbd>

### Whole Document Format

> Windows / Linux: <kbd>Shift+Alt+F</kbd>

![Code formatting](/media/code_formatting.gif)

## Code Folding

> Mac: <kbd>Alt+Cmd+\[</kbd> and <kbd>Alt+Cmd+\]</kbd>

> Windows / Linux: <kbd>Ctrl+Shift+\[</kbd> and <kbd>Ctrl+Shift+\]</kbd>

![Code folding](/media/code_folding.gif)

## Select Current Line

> Mac: <kbd>Cmd+I</kbd>

> Windows / Linux: <kbd>Ctrl+I</kbd>

![Select current line](/media/select_current_line.gif)

## Navigate to Beginning and End of File

> Mac: <kbd>Cmd+&#x2191;</kbd> and <kbd>Cmd+&#x2193;</kbd>

> Windows: <kbd>Ctrl+&#x2191;</kbd> and <kbd>Ctrl+&#x2193;</kbd>

> Linux: <kbd>Ctrl+Home</kbd> and <kbd>Ctrl+End</kbd>

![Navigate to beginning and end of file](/media/beginning_end_file.gif)

## Open Markdown Preview

In a Markdown file, use

> Mac: <kbd>Cmd+Shift+V</kbd>

> Windows / Linux: <kbd>Ctrl+Shift+V</kbd>

![Toggle readme preview](/media/toggle_preview.gif)

## Side by Side Markdown Edit and Preview

In a Markdown file, use

> Mac: <kbd>Cmd+K V</kbd>

> Windows / Linux: <kbd>Ctrl+K V</kbd>

Special bonus: The preview will now sync.

![Markdown sync](/media/markdown-preview-sync.gif)

# IntelliSense

Anytime, try <kbd>Ctrl+Space</kbd> to trigger the Suggestions widget.

![Intellisense](/media/intellisense.gif)

You can view available methods, parameter hints, short documentation, etc.

## Peek

Select a symbol then type <kbd>Alt+F12</kbd>. Alternatively, you can use the context menu.

![Peek](/media/peek.gif)

## Go to Definition

Select a symbol then type <kbd>F12</kbd>. Alternatively, you can use the context menu or <kbd>Ctrl+Click</kbd> (<kbd>Cmd+Click</kbd> on macOS).

![Go to definition](/media/goto_definition.gif)

You can go back to your previous location with the **Go** > **Back** command or <kbd>Alt+&#x2190;</kbd> (<kbd>Ctrl+-</kbd> on macOS).

## Find All References

Select a symbol then type <kbd>Shift+F12</kbd>. Alternatively, you can use the Context Menu.

![Find all references](/media/find_all_references.gif)

## Rename Symbol

Select a symbol then type <kbd>F2</kbd>. Alternatively, you can use the Context Menu.

![Rename symbol](/media/rename_symbol.gif)

## .eslintrc.json

Install the [ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint). Configure
your linter however you'd like. Specification is [here](http://eslint.org/docs/user-guide/configuring).

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

See IntelliSense for your `package.json` file.

![package json intellisense](/media/package_json_intellisense.gif)

## Emmet Syntax

[Support for Emmet syntax](https://code.visualstudio.com/docs/languages/html#_emmet-snippets).

![emmet syntax](/media/emmet_syntax.gif)

# Snippets

## Create Custom Snippets

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

See more details in [Creating your own Snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets).

# Git Integration

Git Integration comes with VS Code "in-the-box". You can install other SCM providers from the extension Marketplace. This section describes the Git integration but much of the UI and gestures are shared by other SCM providers.

## Diffs

Click the Source Control button in the Activity Bar then select the file to diff.

![Git icon](/media/git_icon.png)

**Side by side**

Default is side by side diff.

![Git diff side by side](/media/git_side_by_side.png)

**Inline view**

Toggle inline view by clicking the **More** (...) button in the top right and selecting **Switch to Inline View**.

![More git button](/media/more_button.png)

![Git inline](/media/git_inline.png)

If you prefer the inline view, you can set `"diffEditor.renderSideBySide": false`.


**Review Pane**

Navigate through diffs with <kbd>F7</kbd> and <kbd>Shift+F7</kbd>. This will present them in a unified patch format.
Lines can be navigated with arrow keys and pressing <kbd>Enter</kbd> will jump back in the diff editor and the selected line.

![Diff_review_pane](/media/diff_review_pane.png)


**Edit Pending Changes**

You can make edits directly in the pending changes of the diff view.


## Branches

Easily switch between Git branches via the Status Bar.

![Switch branches](/media/switch_branches.gif)

## Staging

**Stage all**

Hover over the number of files and click the &#x2b; button.

![Git stage all](/media/git_stage_all.gif)

**Stage Selected**

Stage a portion of a file by selecting that file (using the arrows) and then choosing **Stage Selected Ranges** from the **Command Palette**.

![Git stage selected](https://cloud.githubusercontent.com/assets/1926584/23407797/ebeefbb4-fdc5-11e6-8ca1-c4c6c056a8fd.png)

## Undo Last Commit

![Undo last commit](/media/undo_last_commit.gif)

## See Git output

VS Code makes it easy to see what Git commands are actually running. This is helpful when learning Git or debugging a difficult source control issue.

> Mac: <kbd>Shift+Cmd+U</kbd>

> Windows / Linux: <kbd>Ctrl+Shift+U</kbd>

to run `toggleOutput`. Select **Git** in the drop-down.

## Gutter Indicators

View diff decorations in editor. See [documentation](https://code.visualstudio.com/docs/editor/versioncontrol#_gutter-indicators) for more details.

![Git gutter indicators](/media/editingevolved_gutter.png)

## Resolve Merge Conflicts

During a merge, click the Source Control button in the Activity Bar and make changes in the diff view. Select and accept current, incoming or both changes in just one click.

![Git icon](/media/git_icon.png)
![Resolve merge conflicts](/media/resolve_merge_conflicts.gif)

## Setup VS Code as Default Merge Tool

```bash
git config --global merge.tool code
```
## Pull Request Extension

Review pull requests inside VS Code [vscode-pull-request-github](https://github.com/Microsoft/vscode-pull-request-github)

# Debugging

## Configure Debugger

Press <kbd>F1</kbd>, select **Debug: Open launch.json** and select the environment. This will generate a `launch.json` file. Works out of the box as expected for Node.js and other environments. May need some additional configuration for other languages. See [documentation](https://code.visualstudio.com/docs/editor/debugging) for more details.

![Configure debugging](/media/configure_debug.gif)

## Breakpoints and Stepping through

Place breakpoints next to the line number. Navigate forward with the Debug widget.

![debug](/media/node_debug.gif)

## Data inspection

Inspect variables in the Debug panels and in the console.

![data inspection](/media/debug_data_inspection.gif)

## Inline values

You can set `"debug.inlineValues": true` to see variable values inline in the debugger. This feature is experimental and disabled by default.

# Task Runner

## Auto detect tasks

Select **Tasks** from the top-level menu, run the command **Configure Tasks...**, then select the type of task you'd like to run.
This will generate a `tasks.json` file with content like the following. See the Tasks [documentation](https://go.microsoft.com/fwlink/?LinkId=733558) for more details.

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

There are occasionally issues with auto generation. Check out the documentation for getting things to work properly.

## Run tasks from the Tasks menu

Select **Tasks** from the top-level menu, run the command **Run Task...**, and select the task you want to run. Terminate the running task by running the command **Terminate Task...**

![Task runner](/media/task_runner.gif)


## Other Resources

* [VSCode Official Docs](https://code.visualstudio.com/docs)
* [React Sample App](https://github.com/Microsoft/vscode-react-sample)
* [awesome-vscode](https://github.com/viatsko/awesome-vscode)
* [VSCode Can Do That?!](https://vscodecandothat.com/) 
