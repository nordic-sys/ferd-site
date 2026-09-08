# ferd-site

A **Ferð** alkalmazás nyilvános oldala: `https://ferd.nordic-sys.com`

## Miért külön repó

A termék-repó (`nordic-sys/ferd`) **privát**, és az is marad: árazási elemzéseket,
üzleti dokumentációt és belső átvizsgálásokat tartalmaz. A GitHub Pages viszont
publikus repót kíván, ezért a site külön él.

*(A Helsánál a monorepó publikus, és a `site/` benne van — az a repó szándékosan
tisztított történettel épült. Ezé nem, és nem is kell.)*

## Felépítés

Három statikus HTML-oldal és egy stíluslap. **Nincs build-lépés**, nincs függőség:
a GitHub Pages a `main` ág gyökeréből szolgálja ki.

| Fájl | Mi |
|---|---|
| `index.html` | landing, magyarul és angolul |
| `privacy.html` | adatvédelmi tájékoztató — **az App Store és a Play Console ezt az URL-t kéri** |
| `support.html` | támogatás — az App Store Support URL-je |
| `CNAME` | `ferd.nordic-sys.com` |

Ha később rendes landing page kell, ez nőhet Astróvá, ahogy a Helsáé — de egy
adatvédelmi tájékoztatóhoz a build-lépés csak plusz hibalehetőség.

## DNS

`ferd` CNAME → `nordic-sys.github.io.` (a szervezeti domain, repó-útvonal nélkül;
a GitHub a `Host` fejlécből találja meg a repót). A rekordot Pleskben szerkeszted,
onnan szinkronizál a DigitalOceanre — az autoritatív névszerverek az övék.

## ⚠️ Amit együtt kell tartani a termék-repóval

Az adatvédelmi tájékoztató **állítást tesz az app viselkedéséről**. Ha az app valaha
adatot gyűjtene, hálózatot használna vagy harmadik feles SDK-t kapna, ez az oldal
**előbb** változik, mint a kiadás — az App Store adatvédelmi címkéjével együtt.

Ez a `nordic-sys/ferd` repó `CLAUDE.md`-jében is szerepel, hogy ne csak itt legyen
leírva.
