
# Useful Latex Stuff

- [Table Code generator](https://www.tablesgenerator.com/)
- $\frac{x}{y^{asf}}$ 
- $$hkjhkjh$$
- Shortcuts for Bold, Underline, Italics and Links LaTeX VSCode
	- File->Preferences->Keyboard Shortcuts ->Open Keyboard Shortcuts(JSON)(icon in top right corner)-> Then do the following
```JSON
// Place your key bindings in this file to override the defaults

[
    {
        "key": "ctrl+b",
        "command": "editor.action.insertSnippet",
        "when": "editorLangId == latex && editorTextFocus",
        "args": {
            "snippet": "\\textbf{${TM_SELECTED_TEXT}$0}"
        }
    },
    {
        "key": "ctrl+i",
        "command": "editor.action.insertSnippet",
        "when": "editorLangId == latex && editorTextFocus",  // chained clause
        "args": {
            "snippet": "\\textit{${TM_SELECTED_TEXT}$0}"
        }
    },
    {
        "key": "ctrl+u",
        "command": "editor.action.insertSnippet",
        "when": "editorLangId == latex && editorTextFocus",  // chained clause
        "args": {
            "snippet": "\\underline{${TM_SELECTED_TEXT}$0}"
        }
    },
    {
        "key": "ctrl+l",
        "command": "editor.action.insertSnippet",
        "when": "editorLangId == latex && editorTextFocus",  // chained clause
        "args": {
            "snippet": "\\href{${TM_SELECTED_TEXT}$0}{\\textcolor{blue}{\\underline{}}}"
        }
    }
]
```