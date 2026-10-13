# 相模原市 車椅子アクセスマップ

OpenStreetMap（OSM）に登録されている車椅子アクセス情報（`wheelchair` タグ）を使い、相模原市内の施設を地図上に表示するハッカソン作品です。


## 着想

SotM Asia 2026 Osaka の ** Wheelmap** に着想を得て、相模原市の車椅子アクセスマップを作成しました。

## 概要

- 相模原市内で `wheelchair` タグが付いている施設のうち、5件を Leaflet.js の地図にピンで表示します。
- ピンをクリックすると、施設名、種別、車椅子での利用可否が表示されます。車椅子対応トイレ（`toilets:wheelchair`）の情報がある施設は、その情報も表示します。OSM の該当ページへのリンクもあります。

| 場所 | 種別 | wheelchair | 車椅子対応トイレ |
|---|---|---|---|
| 相模大野駅 | 駅 | yes | – |
| 北里大学病院 | 病院 | yes | yes |
| 相模原市立博物館 | 博物館 | yes | – |
| 相模原市立図書館 | 図書館 | yes | yes |
| 相模湖駅前公衆便所 | 公衆トイレ | yes | – |

データは 2026年10月13日に Overpass API で取得しました。

## アクセスマップ

GitHub 上では、下の地図を拡大・縮小できます。ピンをクリックすると施設の情報が表示されます。

```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": { "type": "Point", "coordinates": [139.4378867, 35.5321708] },
      "properties": { "name": "相模大野駅", "種別": "駅", "wheelchair": "yes", "osm": "https://www.openstreetmap.org/node/264240113" }
    },
    {
      "type": "Feature",
      "geometry": { "type": "Point", "coordinates": [139.3931145, 35.5381675] },
      "properties": { "name": "北里大学病院", "種別": "病院", "wheelchair": "yes", "toilets:wheelchair": "yes", "osm": "https://www.openstreetmap.org/node/1420814835" }
    },
    {
      "type": "Feature",
      "geometry": { "type": "Point", "coordinates": [139.3930755, 35.5593079] },
      "properties": { "name": "相模原市立博物館", "種別": "博物館", "wheelchair": "yes", "osm": "https://www.openstreetmap.org/node/1420828722" }
    },
    {
      "type": "Feature",
      "geometry": { "type": "Point", "coordinates": [139.392913, 35.567575] },
      "properties": { "name": "相模原市立図書館", "種別": "図書館", "wheelchair": "yes", "toilets:wheelchair": "yes", "osm": "https://www.openstreetmap.org/node/1420828741" }
    },
    {
      "type": "Feature",
      "geometry": { "type": "Point", "coordinates": [139.1898241, 35.6169398] },
      "properties": { "name": "相模湖駅前公衆便所", "種別": "公衆トイレ", "wheelchair": "yes", "osm": "https://www.openstreetmap.org/node/3353550337" }
    }
  ]
}
```

ピンの表示やポップアップをより作り込んだ地図は、[index.html](index.html) をブラウザで開くと見られます。

## 使用技術

- **OpenStreetMap**：地図タイルと施設の車椅子アクセス情報
- **Overpass API**：相模原市内の `wheelchair` タグ付き施設の検索
- **Leaflet.js**（v1.9.4）：Web地図の表示
- **HTML / JavaScript**：`index.html` だけで動くシンプルな構成
- **Claude Code**：コードの作成支援
- **GitHub**：ソースコードの管理と公開

## 使い方

`index.html` をブラウザで開くと地図が表示されます。地図タイルとLeaflet.jsを読み込むため、インターネット接続が必要です。

## 目的

車椅子利用者が外出先のバリアフリー情報を事前に知ることができ、誰もが安心して外出できる環境づくりに貢献することを目指します。

## ライセンス

本プロジェクトは [クリエイティブ・コモンズ 表示 4.0 国際（CC BY 4.0）](https://creativecommons.org/licenses/by/4.0/deed.ja) ライセンスの下で提供されています。詳しくは [LICENSE](LICENSE) ファイルを参照してください。

## データ・出典

地図データと施設情報は © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) です。これらのデータには ODbL（Open Database License）が適用されます。
