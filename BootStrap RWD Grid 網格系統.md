[]

| 參數項目                      | `特小(xs)`              | `小(sm)`               | `中(md)`               | `大(lg)`               | `特大(xl)`              | `超大(xxl)`             |
| ------------------------- | --------------------- | --------------------- | --------------------- | --------------------- | --------------------- | --------------------- |
| `類別前綴`<br>`(ClassPrefix)` | `.col-`               | `.col-sm-`            | `.col-md-`            | `.col-lg-`            | `.col-xl-`            | `.col-xxl-`           |
| `中斷點`<br>`(Breakpoint)`   | `小於`<br>`576px`       | `大=於`<br>`576px`      | `大=於`<br>`768px`      | `大=於`<br>`992px`      | `大=於`<br>`1200px`     | `大=於`<br>`1400px`     |
| `最大寬度`<br>`(min-width)`   | `100%`                | `540px`               | `720px`               | `960px`               | `1140px`              | `1320px`              |
| `欄位數量`<br>`(Columns)`     | `12`                  | `12`                  | `12`                  | `12`                  | `12`                  | `12`                  |
| `間距`<br>`(Gutter)`        | `1.5rem` <br>`(24px)` | `1.5rem` <br>`(24px)` | `1.5rem` <br>`(24px)` | `1.5rem` <br>`(24px)` | `1.5rem` <br>`(24px)` | `1.5rem` <br>`(24px)` |
| `可否嵌套`<br>`(Nestable)`    | `是`                   | `是`                   | `是`                   | `是`                   | `是`                   | `是`                   |
| `欄位排序`<br>`(Offsets)`     | `是`                   | `是`                   | `是`                   | `是`                   | `是`                   | `是`                   |
|                           |                       |                       |                       |                       |                       |                       |
### 重點參數說明

1. **中斷點 (Breakpoints)**： 這是網格系統的核心。Bootstrap 使用 `min-width`（最小寬度）的媒體查詢（Media Queries），這意味著樣式會應用於該尺寸**及以上**的所有螢幕。例如，`.col-md-` 會影響中、大、特大尺寸。
    
2. **類別前綴 (Class Prefix)**：
    - 如果你只使用 `.col-6`，它會在所有設備上佔據一半寬度。
    - 如果你使用 `.col-md-6`，它會在 768px 以上顯示為一半寬度，在小於 768px 時預設會自動堆疊（100% 寬度）。
        
3. **欄位數量 (Column Count)**： Bootstrap 預設將每一行（Row）分為 **12 欄**。你可以組合這些欄位，例如 `.col-4` + `.col-8` = 12。
    
4. **間距 (Gutter)**： 這是指欄位之間的水平與垂直距離。在 Bootstrap 5 中，你可以透過 `.g-*` 類別（如 `.gx-5` 或 `.gy-2`）來調整這些間距的大小。
    
5. **容器 (Containers)**：
    - `.container`：根據中斷點設定一個 `max-width`
    - `.container-fluid`：始終保持 `width: 100%`。

---

[範例：手機顯示1欄、平板顯示2欄、桌機顯示4欄]
```
<div class="container mt-5">
  <h2 class="text-center mb-4">響應式網格示範</h2>
  <div class="row g-4">
    <div class="col-12 col-md-6 col-lg-3">
      <div class="p-3 border bg-light text-center">項目 1</div>
    </div>
    <div class="col-12 col-md-6 col-lg-3">
      <div class="p-3 border bg-light text-center">項目 2</div>
    </div>
    <div class="col-12 col-md-6 col-lg-3">
      <div class="p-3 border bg-light text-center">項目 3</div>
    </div>
    <div class="col-12 col-md-6 col-lg-3">
      <div class="p-3 border bg-light text-center">項目 4</div>
    </div>
  </div>
</div>
```
### 程式碼邏輯拆解：

| **螢幕尺寸**         | **使用的類別**   | **呈現效果** | **說明**                    |
| ---------------- | ----------- | -------- | ------------------------- |
| **手機 (< 768px)** | `.col-12`   | **單欄**   | 每個區塊佔據滿寬（12/12）。          |
| **平板 (≥ 768px)** | `.col-md-6` | **雙欄**   | 每個區塊佔據一半寬度（6/12），一行放兩個。   |
| **桌機 (≥ 992px)** | `.col-lg-3` | **四欄**   | 每個區塊佔據四分之一寬度（3/12），一行放四個。 |
### 幾個實用的進階技巧：

1. **自動填滿 (`.col`)**：如果你不指定數字，只寫 `.col`，Bootstrap 會自動平均分配剩餘空間。
2. **間距控制 (`.g-*`)**：在 `.row` 加上 `g-3` 或 `g-lg-5`，可以輕鬆調整欄位之間的距離（Gap）。
3. **垂直對齊 (`.align-items-center`)**：如果各欄位高度不同，可以在 `.row` 加上此類別讓它們置中對齊。