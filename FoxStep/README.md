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
    │   │   ├── intro_original.mp4         登場動畫原檔
    │   │   └── shrine-visit_original.mp4  神社現身原檔
    │   └── web/
    │       ├── intro.mp4                  登場動畫（壓縮版，網頁使用）
    │       ├── intro_poster.jpg           登場動畫封面
    │       ├── shrine-visit.mp4           神社現身（裁切＋壓縮版，網頁使用）
    │       └── shrine-visit_poster.jpg    神社現身封面
    └── mascots/                      三位妖狐的圖檔，各有三種表情
        ├── gold-kitsune-miko_{normal,happy,worried}.svg / .png    金髮狐娘
        ├── white-kitsune-miko_{normal,happy,worried}.svg / .png   白髮狐娘
        └── little-white-fox_{normal,happy,worried}.svg / .png     小狐狸
```

## 素材在網頁裡的用途

| 素材 | 出現的時機 |
|---|---|
| `intro.mp4` | 在大廳切換成「金髮狐娘」時全螢幕播放一次，點一下跳過 |
| `shrine-visit.mp4` | 選金髮狐娘時，每走到一座神社（第 7、14、21… 格）跳出來鼓勵 |
| `mascots/*` | 棋盤上的妖狐。網頁裡是用程式碼畫的 SVG，這裡匯出成獨立圖檔 |

## 影片處理紀錄

- **shrine-visit.mp4**：裁掉上方黑邊、左側灰條，以及下方的網站標籤與搜尋按鈕；縮成 480×736，音量拉高到 -18 LUFS。
- **intro.mp4**：縮成 540×960，音量拉高到 -18 LUFS，畫面沒有裁切。
- 兩支都是 H.264 + AAC 的 MP4，Chrome、Edge、Safari、Firefox 都能播放。

## 資料儲存

專案資料存在瀏覽器的 `localStorage`（key：`foxstep.v1`），妖狐樣貌的選擇存在 `foxstep.mascot`。換電腦或換瀏覽器時，用大廳的「匯出全部資料（JSON）」備份，再到新的地方「匯入資料」。
