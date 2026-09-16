---
marp: true
theme: gaia-cust
title: 人工智慧應用開發實務 / Static Web Page
size: 16:9
paginate: true
transition: slide
---

<!-- _class: cover -->
<!-- _paginate: false -->
<!-- _footer: "" -->

# 人工智慧應用開發實務
## Static Web Page
許智超
<cchsu@mail.nsysu.edu.tw>


---

### 地圖 API

Leaflet.js + OpenStreetMap 是製作互動式地圖的常見組合。

- **Leaflet.js**：輕量的 JavaScript 地圖函式庫，負責地圖、標記與互動
- **OpenStreetMap（OSM）**：由社群維護的開放街圖資料
- Leaflet 負責「怎麼顯示」，OSM 提供「顯示什麼地圖」

---

<!-- _class: cols3 -->

### Leaflet 地圖的基本組成

<div class="col-wrap">
<div class="col alt">

**地圖容器**

HTML 預留一個 `div`，Leaflet 將地圖畫在裡面。

</div>
<div class="col alt">

**圖磚圖層**

從地圖服務載入一張張圖磚，拼成完整地圖。

</div>
<div class="col alt">

**圖層與標記**

加入 Marker、Popup、Circle 或 GeoJSON 資料。

</div>
</div>

```text
HTML 容器 → Leaflet 地圖 → OSM 圖磚
↘ 標記、彈出視窗、路線
```

---

### 使用 OpenStreetMap 的注意事項

- 顯示圖磚時，必須保留 `OpenStreetMap` attribution
- 遵守 [OpenStreetMap Tile Usage Policy](https://operations.osmfoundation.org/policies/tiles/)
- 不要大量下載、快取或模擬正常使用者請求
- 商業或高流量服務應選擇合適的圖磚服務商
- OpenStreetMap 是地圖資料來源，不等於完整的導航或地址搜尋 API

---

### SWP06 地圖資訊



---

<!-- _class: cols -->

### 雙欄排版示範

<div class="col-wrap">
<div>

Left content

</div>
<div>

Right content

</div>
</div>

---

<!-- _class: cols3 -->

### 標題

<div class="col-wrap">
<div>

第一欄內容

</div>
<div>

第二欄內容

</div>
<div>

第三欄內容

</div>
</div>