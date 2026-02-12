我們可以設定一個**「全能型」**的快捷鍵：
- 如果你**沒有選取文字**，它會直接噴出 `<?php ?>` 並把游標停在中間。
- 如果你**選取了一段代碼**，它會直接把該段代碼包進 `<?php ... ?>` 裡面。

### 第一步：開啟快捷鍵設定檔
1. 按下 `Ctrl` + `Shift` + `P` (Mac: `Cmd` + `Shift` + `P`)。
2. 輸入 `shortcuts`，選擇 **「開啟鍵盤快速鍵 (JSON)」** (Open Keyboard Shortcuts (JSON))。

### 第二步：貼入設定
在開啟的 `keybindings.json` 檔案的中括號 `[ ]` 內，貼上這段代碼（如果裡面已經有其他設定，記得加逗號隔開）：
```json
{
    "key": "alt+p",
    "command": "editor.action.insertSnippet",
    "when": "editorTextFocus && editorLangId == 'php'",
    "args": {
        "snippet": "<?php ${TM_SELECTED_TEXT}$0 ?>"
    }
}
```

### 如何使用？

1. **包覆現有代碼：** 反白選取你要包起來的 code，按下 `Alt` + `P`。
2. **直接產生標籤：** 不選取任何東西，直接按 `Alt` + `P`。

### 是否成功？
==如果想換成其他組合鍵（例如 `Ctrl` + `Enter`）只要修改上面 `"key"` 的部分即可==