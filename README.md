# 和美高中 115-1 走跳卡里善

這是「走跳卡里善」課程的長期教材 repo。各次上課的投影片與講義原稿放在 `lessons/`，由課程首頁集中列出入口；後續單元沿用同一套樣式與投影片引擎。

目前單元：**2026-09-14「該去買車票了嗎？」，共 24 張投影片**。從第一週「要不要留彰化」接下去：彰化二戰以來人口淨移出、清代劉銘傳在台中規劃省城、1895 年民政支部四個月內從彰化遷往台中、路徑依賴，最後回到「和美需要什麼」。

線上版：<https://folldark.github.io/kalisian-class/>

## 目錄結構

```text
kalisian-class/
├── index.html                    # 課程首頁與單元列表
├── styles.css                    # 首頁與各單元共用樣式（磚紅／砂色色票）
├── app.js                        # 各單元共用投影片引擎（與 research-writing-class 相同）
├── favicon.svg
├── .nojekyll
├── .gitignore
├── README.md
└── lessons/
    └── 2026-09-14-該去買車票了嗎/
        ├── index.html            # 本次投影片
        └── 講義原稿.md            # Obsidian 原稿的副本，不由程式覆寫
```

## 本地預覽

在專案根目錄執行：

```bash
python3 -m http.server 8000
```

以瀏覽器開啟 <http://localhost:8000>，從課程首頁進入單元。結束預覽時，在 Terminal 按 `Ctrl+C`。

全站是純靜態 HTML／CSS／JavaScript，不需要套件安裝或建置步驟，不依賴外部 CDN。字型使用 macOS 內建的 PingFang TC、Songti TC（史料引文），以及 Microsoft JhengHei、system-ui 等常見系統字型。站內檔案採相對路徑，可直接用於 GitHub Pages 的 repository 子路徑。

## 操作方式

| 按鍵／操作 | 功能 |
| --- | --- |
| `←`／`→`、`PageUp`／`PageDown` | 上一張／下一張 |
| `Space`／`Enter` | 下一張 |
| `Home`／`End` | 第一張／最後一張 |
| `F` | 進入或離開全螢幕 |
| `N` | 開啟或關閉講者備註 |
| `Esc` | 關閉備註或操作說明 |
| 左右滑動 | 觸控換頁 |
| 底部控制列 | 換頁、備註、全螢幕、說明與返回課程首頁 |

## 日後新增單元

1. 在 `lessons/` 建立 `YYYY-MM-DD-單元名稱/`，把新原稿存成 `講義原稿.md`，圖片放進該資料夾的 `assets/`。
2. 複製既有單元的 `index.html` 作為骨架，更改 `<title>`、description、`data-title`、日期與封面資訊，替換 `<main class="deck">` 內的投影片內容。維持 `lang="zh-Hant-TW"`。
3. 每張投影片保留 `class="slide"`、`id="slide-N"`、`data-section`、`data-theme` 與 `aria-labelledby`；主題色可用 `brick`（深磚紅）、`charcoal`（炭黑）、`sand`（砂色）、`paper`（米白）。頁數與進度由 `app.js` 自動計算，只需更新控制列的 `#counter` 初始值。
4. 依內容選用 `title-slide`、`section-slide`（長標題加 `long-title`）、`statement-slide`、`question-slide`、`reason-slide`。史料引文用 `<blockquote class="historical-quote">`，年表用 `<ol class="timeline">`，距離對照用 `<ol class="distance-list">`。講者提示放在 `<aside class="speaker-notes">`，不擴寫原稿正文；沒有實質提示就不要放。
5. 共用檔案繼續引用 `../../styles.css`、`../../app.js`、`../../favicon.svg`；單元圖片用 `assets/圖片.png`。
6. 在根目錄 `index.html` 的 `.lesson-list` 複製一個 `<li>`，更新入口相對路徑、日期、名稱與一句話說明；README 的「目前單元」也補一行。
7. 本地預覽，檢查正文、投影畫面、手機、換頁與連結。

## 設計與內容說明

- 正文逐字保留 Obsidian 原稿的語氣；補充、老師自己的例子與史料批判放在講者備註，投影片上不出現。
- 2026-09-14 單元第 16 張引用《臺灣新民報》1933 年彰化特輯中津德治的「八卦山軍事危險」說。該說法是 1933 年的事後回顧，兒玉源太郎 1898 年才就任總督，1909 年廢彰化廳與 1895 年民政支部遷移也是不同事件，所以投影片標題保留問號，備註寫明不能直接當作 1895 年遷治的官方理由。完整考證在 Obsidian 的 1933 新民報對照稿。
- 第 21 張的三段距離刻意留白讓學生自己查；備註的參考值未經實測，上課前請再確認。

## 授權

課程文字與投影片設計保留所有權利。未經授權，請勿重製或另行散布。引用的史料（劉銘傳奏摺、《臺灣新民報》）權利歸原出處所有。
