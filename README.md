# 別府ごはん検索 — Vercel公開手順

1. このフォルダをそのまま GitHub にプッシュ（または Vercel の "Add New Project" でフォルダをドラッグ）
2. Framework Preset は「Other」、Build Command なし、Output Directory は空のまま → Deploy
3. 発行された URL（例：https://beppu-gohan.vercel.app）を Instagram の bio リンクに

## お店を追加する

index.html の `const STORES = [` の中に1行足すだけ：

{ name:{ja:"店名", en:"Name"}, area:"beppu_sta", genre:"ramen", tags:["lunch","parking"],
  price:900, note:{ja:"一言", en:"One line"}, ig:"https://www.instagram.com/p/xxxx/", map:"https://www.google.com/maps/search/店名+別府" },

- area：beppu_sta(別府駅周辺) / ishigaki(石垣) / tsurumi(鶴見) / shonin(上人) / kannawa(鉄輪) / kamegawa(亀川) / horita(堀田) / oita(大分市) / yufuin(湯布院)
- genre：teishoku / ramen / soba / sushi / yakiniku / cafe / sweets / bread / izakaya / western / chinese
- tags：lunch / dinner / kids / parking / takeout / anniversary / solo / late / view / sweets_t / english
- 地図のエリア位置は `AREA_POS`、朱印の短い地名は `STAMP` に追加
- 新しいエリア・ジャンル・条件は DICT に ja/en を追加すれば自動でボタンになる
- 言語は ja/en/ko/tw(繁体)/cn(簡体) の5つ。各店の name と note にこの5つを書く（足りない言語は英語で表示される）
