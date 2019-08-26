# [VS Code](https://code.visualstudio.com) Tips and Tricks

>**Note**: Tips and Tricks has moved to the official Visual Studio Code documentation at [code.visualstudio.com](https://code.visualstudio.com/docs/getstarted/tips-and-tricks).<BR>
>The content is now at [vscode-docs](https://github.com/Microsoft/vscode-docs/blob/master/docs/getstarted/tips-and-tricks.md). Pull requests and documentation issues are still greatly appreciated.

# Table of Contents

1. <a href="#basics">Basics</a>
2. <a href="#customization">Customization</a>
3. <a href="#extensions">Extensions</a>
4. <a href="#file-and-folder-management">File and folder management</a>
5. <a href="#editing-hacks">Editing hacks</a>
6. <a href="#intellisense">IntelliSense</a>
7. <a href="#snippets">Snippets</a>
8. <a href="#git-integration">Git integration</a>
9. <a href="#debugging">Debugging</a>
10. <a href="#task-runner">Task runner</a>
11. <a href="#other-resources">Other Resources</a>

> The key bindings below may or may not be accurate with the latest build. See [here](https://code.visualstudio.com/docs/getstarted/keybindings) for the latest keyboard shortcut reference.

# Basics

## Insider Version of VS Code

The Visual Studio Code team uses the Insiders version to test the latest features and bug fixes of VS Code. You can use this same version by [downloading here](https://code.visualstudio.com/insiders).

* For Early Adopters - Insiders has the most recent code changes and may lead to the occasional broken build.
* Frequent Builds - New builds everyday with the latest bug fixes and features.
* Side-by-side install - Insiders installs next to the Stable build allowing you to use either independently.

![side by side install](/media/side-by-side-install.png)

## Getting Started

Open the **Welcome** page to get started with the basics of VS Code. **Help** > **Welcome**.

![welcome page](/media/welcome_page.png)

Includes the **Interactive Playground**.

![interactive playground](/media/interactive_playground.png)

## Command Palette

Access all available commands based on your current context.

> Mac: <kbd>cmd+shift+p</kbd> or <kbd>f1</kbd>

> Windows / Linux: <kbd>ctrl+shift+p</kbd> or <kbd>f1</kbd>

![command palette](/media/OpenCommandPalatte.gif)

## Reference keybindings

All of the commands are in the **Command Palette** with the associated key binding (if it exists). If you forget what the key binding is use the **Command Palette** to help you out.

![keyboard references](/media/keyboard-references.png)

## Quick open

Quickly open files.

> Mac: <kbd>cmd+p</kbd>

> Windows / Linux: <kbd>ctrl+p</kbd>

![Quick Open](/media/QuickOpen.gif)

> **Tip:** Type "?" to view help suggestions.

### Navigate between recently opened files

Repeat the **Quick Open** keyboard shortcut to cycle quickly between recently opened files.

### Open multiple files from Quick Open

You can open multiple files from **Quick Open** by pressing the Right arrow key. This will open the currently selected file in the background and you can continue selecting files from **Quick Open**.

## CLI tool

> Linux: Follow instructions [here](https://code.visualstudio.com/docs/setup/linux).

> Windows: Follow instructions [here](https://code.visualstudio.com/docs/setup/windows).

> Mac: see below.

Open the **Command Palette** (<kbd>F1</kbd>) and type "shell command". Hit enter to execute **Shell Command: Install 'code' command in PATH**.

![shell command](/media/setup_shell-command.png)


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

![all cli commands](/media/vscode-cli-commands.png)

## .vscode folder

Workspace specific files are in `.vscode`. For example, `tasks.json` for the Task Runner and `launch.json` for the debugger.

## Status Bar decorations

**Errors and Warnings**

> Mac: <kbd>shift+cmd+m</kbd>

> Windows / Linux: <kbd>ctrl+shift+m</kbd>

Quickly jump to errors and warnings in the project.

Cycle through errors with <kbd>f8</kbd> or <kbd>shift+f8</kbd>

![errors and warnings](/media/Errors_Warnings.gif)

You can filter problems by type ('errors', 'warnings') or text matching.

**Change language mode**

> Mac: <kbd>cmd+k m</kbd>

> Windows / Linux: <kbd>ctrl+k m</kbd>

![change syntax](/media/change_syntax.gif)

If you want to persist the new language mode for that file type, you can use the **Configure File Association for ...** command to associate the current file extension with an installed language.

# Customization

There are many things you can do to customize VS Code.

* Change your theme
* Change your keyboard shortcuts
* Tune your settings
* Add JSON validation
* Create snippets
* Install extensions

Check out the full [documentation](https://code.visualstudio.com/docs/getstarted/settings).

## Change your theme

Open the **Command Palette** and type "themes". You can install more themes from the extension Marketplace.

![Preview themes](/media/PreviewThemes.gif)

Additionally, you can install and change your File Icon themes.

![File icon themes](/media/PreviewFileIconThemes.gif)

## Change your keyboard shortcuts

### Keyboard Reference Sheets

Download the keyboard shortcut reference sheet for your platform ([macOS](https://go.microsoft.com/fwlink/?linkid=832143), [Windows](https://go.microsoft.com/fwlink/?linkid=832145), [Linux](https://go.microsoft.com/fwlink/?linkid=832144)).

![Keyboard Reference Sheet](/media/KeyboardReferenceSheet.png)

### Keymaps

Are you used to keyboard shortcuts from another editor? You can install a Keymap extension that brings the keyboard shortcuts from your favorite editor to VS Code. Go to **Preferences** > **Keymap Extensions** to see the current list on the [Marketplace](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads). Some of the more popular ones:

- [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)
- [Sublime Text Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.sublime-keybindings)
- [Emacs Keymap](https://marketplace.visualstudio.com/items?itemName=hiro-sun.vscode-emacs)
- [Atom Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.atom-keybindings)
- [Eclipse Keymap](https://marketplace.visualstudio.com/items?itemName=alphabotsec.vscode-eclipse-keybindings)

### Customize your keyboard shortcuts

Open the **Command Palette** and type "keyboard shortcuts." You can now add your own keybindings in the file on the right.

![customize keyboard shortcuts](/media/KeyboardShortcuts.gif)

See more in [Key Bindings for Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings).

## Tune your settings

Open `settings.json`

> Mac: <kbd>cmd+,</kbd>

> Windows / Linux: **File** > **Preferences** > **Settings** or <kbd>ctrl+,</kbd>

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

![font ligatures](/media/font-ligatures-annotated.png)

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

## Language specific settings

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

## Find extensions

1. In the VS Code [Marketplace](https://marketplace.visualstudio.com/vscode).
2. Search inside VS Code
3. View extension recommendations
4. Community curated extension lists, such as [awesome-vscode](https://github.com/viatsko/awesome-vscode)

## Install extensions

Click the Extensions Activity Bar button. You can search via the search bar or click the **More** (...) button to filter and sort by install count.

![install extensions](/media/InstallExtensions.gif)

## Extension recommendations

Click the Extensions Activity Bar button. Then click **Show Recommended Extensions** in the **More** (...) button menu.

![show recommended extensions](/media/ShowRecommendedExtensions.gif)

## Creating my own extension

Are you interested in creating your own extension? You can learn how to do this in the documentation, specifically check out the [documentation on contribution points](https://code.visualstudio.com/docs/extensionAPI/extension-points). A simple "Hello, world" tutorial can be found [here](https://code.visualstudio.com/docs/extensions/example-hello-world).

* configuration
* commands
* keybindings
* languages
* debuggers
* grammars
* themes
* snippets
* jsonValidation

# File and folder management

## Integrated terminal

> Windows / Linux / Mac: <kbd>ctrl+`</kbd>

![Integrated terminal](/media/integrated_terminal.png)

Further reading:

- [Official documentation](https://code.visualstudio.com/docs/editor/integrated-terminal)
- [Mastering VS Code's Terminal article](http://www.growingwiththeweb.com/2017/03/mastering-vscodes-terminal.html)


## Auto Save

Open `settings.json` with <kbd>cmd+,</kbd>

```json
"files.autoSave": "afterDelay"
```

You can also toggle Auto Save from the top-level menu with the **File** > **Auto Save**.

## Toggle Sidebar

> Mac: <kbd>cmd+b</kbd>

> Windows / Linux: <kbd>ctrl+b</kbd>

![toggle side bar](/media/toggle_side_bar.gif)

## Zen Mode

> Mac: <kbd>cmd+k z</kbd>

> Windows / Linux: <kbd>ctrl+k z</kbd>

![zen mode](/media/zen_mode.gif)

Enter distraction free Zen mode.

## Side by side editing

> Mac: <kbd>cmd+\\</kbd> or <kbd>cmd</kbd> then click a file from the File Explorer.

> Windows / Linux: <kbd>ctrl+\\</kbd>

> Linux: <kbd>ctrl+2</kbd>

![split editors](/media/split_editor.gif)

You can use drag and drop editors to create new editor groups and move editors between groups.

## Switch between editors

> Mac: <kbd>cmd+1</kbd>, <kbd>cmd+2</kbd>, <kbd>cmd+3</kbd>

> Windows / Linux: <kbd>ctrl+1</kbd>, <kbd>ctrl+2</kbd>, <kbd>ctrl+3</kbd>

![navigate editors](/media/navigate_editors.gif)

## Move to Explorer window

> Mac: <kbd>cmd+shift+e</kbd>

> Windows / Linux: <kbd>ctrl+shift+e</kbd>

## Create and open a file

> Mac: <kbd>cmd+click</kbd>

> Windows / Linux: <kbd>ctrl+click</kbd>

![create and open file](/media/create_open_file.gif)

## Close the currently opened folder

> Mac: <kbd>cmd+w</kbd>

> Windows / Linux: <kbd>ctrl+k f</kbd>

## History

Navigate entire history with <kbd>ctrl+tab</kbd>

Navigate back.

> Mac: <kbd>ctrl+-</kbd>

> Windows / Linux: <kbd>alt+left</kbd>

Navigate Forward.

> Mac: <kbd>ctrl+shift+-</kbd>

> Windows / Linux: <kbd>alt+right</kbd>

![navigate history](/media/navigate_history.gif)

## Navigate to a file

> Mac: <kbd>cmd+e</kbd> or <kbd>cmd+p</kbd>

> Windows / Linux: <kbd>ctrl+e</kbd> or <kbd>ctrl+p</kbd>

![navigate to file](/media/navigate_to_file.gif)

## File associations

Create language associations for files that aren't detected accurately (for example, many config files are JSON).

```json
"file.associations": {
    ".database": "json"
}
```

# Editing hacks

Here are a selection of common features for editing code. If the keyboard shortcuts aren't comfortable for you, consider installing a [Keymap extension](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads) for your old editor.

## Multi cursor selection

> Mac: <kbd>opt+cmd+up</kbd> or <kbd>opt+cmd+down</kbd>

> Windows: <kbd>ctrl+alt+up</kbd> or <kbd>ctrl+alt+down</kbd>

> Linux: <kbd>alt+shift+up</kbd> or <kbd>alt+shift+down</kbd>

![multi cursor](/media/multi_cursor.gif)

![multi cursor second example](/media/editingevolved_multicursor.gif)

Add more cursors to current selection.

![add cursor to all occurrences of current selection](/media/add_cursor_current_selection.gif)

## Join line

> Mac: <kbd>ctrl+j</kbd>

> Windows / Linux: Not bound by default. Open Keyboard Shortcuts and bind `editor.action.joinLines` to a shortcut of your choice.

![Join lines](/media/JoinLines.gif)

## Copy line up / down

> Mac: <kbd>opt+shift+up</kbd> or <kbd>opt+shift+down</kbd>

> Windows / Linux([Issue #5363](https://github.com/Microsoft/vscode/issues/5363)): <kbd>shift+alt+down</kbd> or <kbd>shift+alt+up</kbd>

![copy line down](/media/copy_line_down.gif)

## Shrink / expand selection

More in [documentation](https://code.visualstudio.com/docs/editor/editingevolved#_selection-multicursor)

> Mac: <kbd>ctrl+shift+cmd+left</kbd> or <kbd>ctrl+shift+cmd+right</kbd>

> Windows / Linux: <kbd>shift+alt+left</kbd> or <kbd>shift+alt+right</kbd>

![shrink expand selection](/media/shrink_expand_selection.gif)

## Go to Symbol in File

> Mac: <kbd>cmd+shift+o</kbd>

> Windows / Linux: <kbd>ctrl+shift+o</kbd>

![Find by symbol](/media/find_by_symbol.gif)

You can group the symbols by kind by adding a colon, `@:`.

![group symbols by kind](/media/group_symbols_by_kind.png)

## Go to Symbol in Workspace

> Mac: <kbd>cmd+t</kbd>

> Windows / Linux: <kbd>ctrl+t</kbd>

![go to symbol in workspace](/media/go_to_symbol_in_workspace.png)

## Navigate to a specific line

> Mac: <kbd>ctrl+g</kbd> or <kbd>cmd+p, :</kbd>

> Windows / Linux: <kbd>ctrl+g</kbd>

![navigate to line](/media/navigate_to_line.gif)

## Undo cursor position

> Mac: <kbd>cmd+u</kbd>

> Windows / Linux: <kbd>ctrl+u</kbd>

![undo cursor position](/media/undo_cursor_position.gif)

## Move line up and down

> Mac: <kbd>opt+up</kbd> or <kbd>opt+down</kbd>

> Windows / Linux: <kbd>alt+up</kbd> or <kbd>alt+down</kbd>

![move line up and down](/media/move_line.gif)

## Trim trailing whitespace

> Mac: <kbd>cmd+k cmd+x</kbd>

> Windows / Linux: <kbd>ctrl+k</kbd> <kbd>ctrl+x</kbd>

![trailing whitespace](/media/trim_whitespace.gif)

## Code formatting

### Currently selected source code

> Mac: <kbd>cmd+k, cmd+f</kbd>

> Windows / Linux: <kbd>ctrl+k, ctrl+f</kbd>

### Whole document format

> Windows / Linux: <kbd>shift+alt+f</kbd>

![code formatting](/media/code_formatting.gif)

## Code folding

> Mac: <kbd>alt+cmd+\[</kbd> and <kbd>alt+cmd+\]</kbd>

> Windows / Linux: <kbd>ctrl+shift+\[</kbd> and <kbd>ctrl+shift+\]</kbd>

![code folding](/media/code_folding.gif)

## Select current line

> Mac: <kbd>cmd+i</kbd>

> Windows / Linux: <kbd>ctrl+i</kbd>

![select current line](/media/select_current_line.gif)

## Navigate to beginning and end of file

> Mac: <kbd>cmd+up</kbd> and <kbd>cmd+down</kbd>

> Windows: <kbd>ctrl+up</kbd> and <kbd>ctrl+down</kbd>

> Linux: <kbd>ctrl+home</kbd> and <kbd>ctrl+end</kbd>

![navigate to beginning and end of file](/media/beginning_end_file.gif)

## Open Markdown Preview

In a Markdown file, use

> Mac: <kbd>shift+cmd+v</kbd>

> Windows / Linux: <kbd>ctrl+shift+v</kbd>

![toggle readme preview](/media/toggle_preview.gif)

## Side by Side Markdown Edit and Preview

In a Markdown file, use

> Mac: <kbd>cmd+k v</kbd>

> Windows / Linux: <kbd>ctrl+k v</kbd>

Special bonus: The preview will now sync.

![markdown sync](/media/markdown-preview-sync.gif)

# IntelliSense

Anytime, try <kbd>ctrl+space</kbd> to trigger the Suggestions widget.

![intellisense](/media/intellisense.gif)

You can view available methods, parameter hints, short documentation, etc.

## Tab completion

Editor Tab completion can now complete all kind of suggestions. After setting "editor.tabCompletion": "on", pressing Tab will complete any prefix, not just snippets. Also, pressing Tab will insert the next suggestion and ⇧Tab will insert the previous suggestion.

![tab completion](https://code.visualstudio.com/assets/updates/1_28/tabcompletion.gif)

## Peek

Select a symbol then type <kbd>alt+f12</kbd>. Alternatively, you can use the context menu.

![peek](/media/peek.gif)

## Go to Definition

Select a symbol then type <kbd>f12</kbd>. Alternatively, you can use the context menu or <kbd>ctrl+click</kbd> (<kbd>cmd+click</kbd> on macOS).

![go to definition](/media/goto_definition.gif)

You can go back to your previous location with the **Go** > **Back** command or <kbd>alt+left</kbd> (<kbd>ctrl+-</kbd> on macOS).

## Find All References

Select a symbol then type <kbd>shift+f12</kbd>. Alternatively, you can use the context menu.

![find all references](/media/find_all_references.gif)

## Rename Symbol

Select a symbol then type <kbd>f2</kbd>. Alternatively, you can use the context menu.

![rename symbol](/media/rename_symbol.gif)

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

## Emmet syntax

[Support for Emmet syntax](https://code.visualstudio.com/docs/languages/html#_emmet-snippets).

![emmet syntax](/media/emmet_syntax.gif)

# Snippets

## Create custom snippets

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

Git integration comes with VS Code "in-the-box". You can install other SCM provider from the extension Marketplace. This section describes the Git integration but much of the UI and gestures are shared by other SCM providers.

## Diffs

Click the Source Control button in the Activity Bar then select the file to diff.

![git icon](/media/git_icon.png)

**Side by side**

Default is side by side diff.

![git diff side by side](/media/git_side_by_side.png)

**Inline view**

Toggle inline view by clicking the **More** (...) button in the top right and selecting **Switch to Inline View**.

![more git button](/media/more_button.png)

![git inline](/media/git_inline.png)

If you prefer the inline view, you can set `"diffEditor.renderSideBySide": false`.


**Review Pane**

Navigate through diffs with `F7` and `Shift+F7`. This will present them in a unified patch format.
Lines can be navigated with arrow keys and pressing `Enter` will jump back in the diff editor and the selected line.

![diff_review_pane](/media/diff_review_pane.png)


**Edit pending changes**

You can make edits directly in the pending changes of the diff view.


## Branches

Easily switch between Git branches via the Status Bar.

![switch branches](/media/switch_branches.gif)

## Staging

**Stage all**

Hover over the number of files and click the plus button.

![git stage all](/media/git_stage_all.gif)

**Stage selected**

Stage a portion of a file by selecting that file (using the arrows) and then choosing **Stage Selected Ranges** from the **Command Palette**.

![git stage selected](https://cloud.githubusercontent.com/assets/1926584/23407797/ebeefbb4-fdc5-11e6-8ca1-c4c6c056a8fd.png)

## Undo last commit

![undo last commit](/media/undo_last_commit.gif)

## See Git output

VS Code makes it easy to see what Git commands are actually running. This is helpful when learning Git or debugging a difficult source control issue.

> Mac: <kbd>shift+cmd+u</kbd>

> Windows / Linux: <kbd>ctrl+shift+u</kbd>

to run `toggleOutput`. Select **Git** in the drop-down.

## Gutter indicators

View diff decorations in editor. See [documentation](https://code.visualstudio.com/docs/editor/versioncontrol#_gutter-indicators) for more details.

![git gutter indicators](/media/editingevolved_gutter.png)

## Resolve merge conflicts

During a merge, click the Source Control button in the Activity Bar and make changes in the diff view. Select and accept current, incoming or both changes in just one click.

![git icon](/media/git_icon.png)
![resolve merge conflicts](/media/resolve_merge_conflicts.gif)

## Setup VS Code as default merge tool

```bash
git config --global merge.tool code
```
## Pull request extension

Review pull requests inside vscode [vscode-pull-request-github](https://github.com/Microsoft/vscode-pull-request-github)

# Debugging

## Configure debugger

<kbd>f1</kbd> and select **Debug: Open launch.json**, select the environment. This will generate a `launch.json` file. Works out of the box as expected for Node.js and other environments. May need some additional configuration for other languages. See [documentation](https://code.visualstudio.com/docs/editor/debugging) for more details.

![configure debugging](/media/configure_debug.gif)

## Breakpoints and stepping through

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

![task runner](/media/task_runner.gif)


## Other Resources

* [vscode official docs](https://code.visualstudio.com/docs)
* [react sample app](https://github.com/Microsoft/vscode-react-sample)
* [awesome vscode](https://github.com/viatsko/awesome-vscode)
* [vscode can do that](https://vscodecandothat.com/) 
