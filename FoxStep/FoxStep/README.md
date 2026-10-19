# 狐步 FoxStep

把專案進度變成一趟旅程的網頁。直接用瀏覽器打開 `index.html` 就能用，不需要網路以外的任何東西（字體會從 Google Fonts 載入，離線時改用系統字體）。

`index.html` 已經把下面的影片和封面圖內嵌在裡面，所以單獨拿 `index.html` 也能完整運作。`assets/` 是同一批素材的獨立檔案，方便你另外使用或修改。

## 資料夾內容

```
FoxStep/
├── index.html                        網頁本體（單一檔案）
├── README.md                         這份說明
├── docs/
│   └── spec.md                       專案規格（你一開始給的）
└── assets/
    ├── images/
    │   └── gold-kitsune-miko.png     金髮狐娘原圖（你的角色設定）
    ├── videos/
    │   ├── original/
    │   │   ├── shrine-visit_original.mp4        金髮狐娘神社現身原檔
    │   │   └── shrine-visit-white_original.mp4  白髮狐娘神社現身原檔
    │   ├── unused/
    │   │   └── intro_original.mp4               金髮狐娘登場動畫原檔（已從網頁拿掉，先保留）
    │   └── web/
    │       ├── shrine-visit.mp4           金髮狐娘神社現身（裁切＋壓縮版，網頁使用）
    │       ├── shrine-visit_poster.jpg    金髮狐娘神社現身封面
    │       ├── shrine-visit-white.mp4     白髮狐娘神社現身（壓縮版，網頁使用）
    │       └── shrine-visit-white_poster.jpg  白髮狐娘神社現身封面
    └── mascots/                      三位妖狐的圖檔，各有三種表情
        ├── gold-kitsune-miko_{normal,happy,worried}.svg / .png    金髮狐娘
        ├── white-kitsune-miko_{normal,happy,worried}.svg / .png   白髮狐娘
        └── little-white-fox_{normal,happy,worried}.svg / .png     小狐狸
```

## 素材在網頁裡的用途

| 素材 | 出現的時機 |
|---|---|
| `shrine-visit.mp4` | 選金髮狐娘時，每走到一座神社（第 7、14、21… 格）跳出來鼓勵 |
| `shrine-visit-white.mp4` | 選白髮狐娘時，每走到一座神社跳出來鼓勵（橫向影片，語氣比較沉穩） |
| `mascots/*` | 棋盤上的妖狐。網頁裡是用程式碼畫的 SVG，這裡匯出成獨立圖檔 |

## 影片處理紀錄

- **shrine-visit.mp4**：裁掉上方黑邊、左側灰條，以及下方的網站標籤與搜尋按鈕；縮成 480×736，音量拉高到 -18 LUFS。
- **shrine-visit-white.mp4**：橫向影片，縮成 768×432，音量拉高到 -18 LUFS，畫面沒有裁切。
- 兩支都是 H.264 + AAC 的 MP4，Chrome、Edge、Safari、Firefox 都能播放。

## 資料儲存

專案資料存在瀏覽器的 `localStorage`（key：`foxstep.v1`），妖狐樣貌的選擇存在 `foxstep.mascot`。換電腦或換瀏覽器時，用大廳的「匯出全部資料（JSON）」備份，再到新的地方「匯入資料」。
