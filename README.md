# scraperde

Install package
```sh
npm i @pitgamer1909/scraperde
```
Install latest version from github (not recommended)
```sh
npm i github:pitgamer1909/scraperde
```

## Was ist aktualisiert worden?
- Verwendung von [zod](https://www.npmjs.com/package/zod) zur Validierung der Dateneingabe und -ausgabe. (noch nicht fertig)
- Einige Fehlerkorrekturen.
- Einschneidende Änderungen. siehe [this](#from-v200-to-v300)
- `didyoumean` hinzugefügt, um nach ähnlichen Wörtern zu suchen.
- Hinzugefügt `snapsave`
- Hinzugefügt `zippyshare`
- Hinzugefügt `sfilemobi`

## Beispiel verwenden
``js
// ESM 
import * as scraper from '@bochilteam/scraper'
// CJS
const scraper = require('@bochilteam/scraper')
```
### Instagram Downloader
```js
// Instagram-Downloader
importieren { 
    instagramdl, 
    instagramdlv2, 
    instagramStory,
    instagramStoryv2
} von '@bochilteam/scraper'
const url = 'https://www.instagram.com/reel/CXK49yFLtJ_/?utm_source=ig_web_copy_link'
instagramdl(url).then(console.log).catch(console.error)
instagramdlv2(url).then(console.log).catch(console.error)
// beide verwenden, um Fehler zu behandeln
instagramdl(url).catch(_ => instagramdlv2(url)).then(console.log)
// Verwenden Sie async/await oder await auf höchster Ebene
console.log(await instagramdl(url).catch(console.error))
console.log(await instagramdlv2(url).catch(console.error))
// Instagram-Story-Downloader
const username = 'freefirebgid'
const story = await instagramStory(username).catch(async _ => await instagramStoryv2(username))
console.log(story)
```
- `instagramdl` use website https://snapinsta.app, 
- `instagramdlv2` benutze Website https://downloadgram.org
- `instagramdlv3` benutze Website https://downvideo.quora-wiki.com
- `instagramdlv4` verwende Website https://instadownloader.co
- InstagramStory" verwendet die Website https://storydownloader.app
- InstagramStoryv2" verwendet die Website https://www.instadp.com [**funktioniert nicht**]


### Youtube Downloader
```js
// Youtube Downloader
importieren { 
    youtubedl,
    youtubedlv2 
} von '@bochilteam/scraper'
const url = 'https://youtu.be/iik25wqIuFo'
youtubedl(url).catch(_ => youtubedlv2(url)).then(({ video }) => {
    video['240p'].download().then(console.log).catch(console.error)
})
// Async/Wawait verwenden 
const yt = await youtubedl(url).catch(async () => await youtubedlv2(url))
const dl_url = await yt.video['240p'].download()
console.log(dl_url)
```
- youtubedl" verwendet die Website https://www.y2mate.com
- `youtubedlv2` benutze Website https://yt5s.com
- youtubedlv3` verwendet die Webseite https://onlinevideoconverter.pro
- `youtubeSearch` verwendet die Website https://www.youtube.com


### Tiktok Downloader
```js
// Tiktok-Downloader
importieren { 
    tiktokdl,
    tiktokdlv2 
} von '@bochilteam/scraper'
// Tiktok-Downloader v1
const url = 'https://www.tiktok.com/@tiktok/video/6844446901010982300'
tiktokdl(url).then(console.log).catch(console.error)
// tiktokdl v2
tiktokdlv2(url).then(console.log).catch(console.error)
// async / await 
console.log(await tiktokdl(url).catch(console.error))
console.log(await tiktokdlv2(url).catch(console.error))
```
- tiktokdl" verwendet die Website https://snaptik.app
- `tiktokdlv2` benutze Website https://api.tikmate.app
- tiktokdlv3`verwende Website 'https://ssstik.io
- `tiktokfyp` use website https://t.tiktok.com [**Nicht funktionierend**]

### All in One Downloader
``js
importieren {
    aiovideodl,
    savefrom,
    snapsave
} von '@bochilteam/scraper'
// Facebook-Video-Downloader
console.log(await aiovideodl('https://fb.watch/9WktuN9j-z/'))
// Twitter-Video-Downloader
console.log(await aiovideodl('https://twitter.com/jen_degen/status/1458167531869458440?s=20'))

// Tiktok-Downloader
console.log(await savefrom('https://www.tiktok.com/@omagadsus/video/7025456384175017243?is_from_webapp=1&sender_device=pc&web_id6982004129280116226'))
// Instagram-Downloader
console.log(await savefrom('https://www.instagram.com/reel/CXK49yFLtJ_/?utm_source=ig_web_copy_link'))

// Instagram-Downloader
console.log(await snapsave('https://www.instagram.com/reel/CXK49yFLtJ_/?utm_source=ig_web_copy_link'))
// Facebook-Video-Downloader
console.log(await snapsave('https://fb.watch/9WktuN9j-z/'))
```
- `aiovideodl` use website https://aiovideodl.ml [**Not Working**]
- `savefrom` use website https://id.savefrom.net
- `snapsave` benutze Website https://snapsave.app

### Aksara Jawa
``js
// Aksara Jawa
importieren { 
    latinToAksara,
    aksaraToLatin
} von '@bochilteam/scraper'
// Lateinisch zu Aksara Jawa
console.log(latinToAksara('hallo rek'))
// Aksara jawa zu Lateinisch
console.log(aksaraToLatin('ꦲꦭ꧀ꦭꦺꦴꦫꦺꦏ꧀', { HVokal: false })) // Hvokal: false bedeutet, dass ꦲ 'ha' und nicht vokal zurückgeben wird.
```
Quelle: https://bennylin.github.io/transliterasijawa/


### Primbons
```js
// Primbons
importieren { 
    getZodiac,
    nomorhoki
} von '@bochilteam/scraper'
// Tierkreiszeichen holen
console.log(getZodiac(1, 1))
// Nomorhoki abrufen
console.log(await nomorhoki(6213353))
```
- artimimpi` verwenden Website https://www.primbon.com
- artiname" verwendet die Website https://www.primbon.com
- nomorhoki` verwenden Website https://www.primbon.com
- `getZodiac` Quelle: https://github.com/Nurutomo/wabot-aq/blob/master/plugins/zodiac.js


### Bilder
``js
// Bilder
importieren {
    googleImage,
    pinterest,
    Hintergrundbild,
    stickerTelegram,
} von '@bochilteam/scraper'
const keyword = 'minecraft'
// Google-Bild
console.log(await googleImage(keyword))
// Pinterest-Bild
console.log(await pinterest(keyword))
// Hintergrundbild
console.log(await wallpaper(Schlüsselwort))
// Aufkleber-Telegramm
console.log(await stickerTelegram(Schlüsselwort))
```
- googleImage" verwendet die Website https://www.google.com
- pinterest" verwendet die Website https://www.pinterest.com
- `stickerTelegram` verwendet die Website https://combot.org
- stickerLine` verwendet die Website https://store.line.me
- `wallpaper` verwende Website https://www.shutterstock.com
- `wallpaperv2` verwende Website https://wall.alphacoders.com
- `wallpaperv3` verwende Website https://www.hdwallpapers.in


### Religionen
```js
// Religionen
importieren {
    asmaulhusna, asmaulhusnajson,
    alquran,
    jadwalsholat, listJadwalSholat
} von '@bochilteam/scraper'
// Asmaul Husna
console.log(await asmaulhusna())
// Asmaul Husna Json
console.log(asmaulhusnajson) // der json wird leer, wenn man `asmaulhusna()` nie benutzt
// alquran 
console.log(await alquran())
// Jadwal Sholat
console.log(await jadwalsholat('semarang'))
```
- `alquran` Quelle: https://raw.githubusercontent.com/rzkytmgr/quran-api/master/data/quran.json
- `asmaulhusna` Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/religi/asmaulhusna.json
- jadwalsholat" verwendet die Website https://www.jadwalsholat.org


### Spiele
```js
// Spiele
importieren {
    tebakgambar, tebakgambarjson,
    asahotak, asahotakjson
} von '@bochilteam/scraper'
// Tebakgambar
console.log(await tebakgambar())
// Tebak gambar json
console.log(tebakgambarjson) // der json wird leer sein, wenn Sie nie `tebakgambar()` verwenden
// Asahotak
console.log(await asahotak())
// Asahotak json
console.log(asahotakjson) // das json wird leer sein, wenn Sie `asahotak()` nie benutzen
```
- `asahotak` Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/asahotak.json
- `caklontong` Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/caklontong.json
- `Familie100` Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/family100.json
- siapakahaku` Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/siapakahaku.json
- Susunkata" Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/susunkata.json
- Tebakbendera" Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/tebakbendera.json
- stebakgambar" Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/tebakgambar.json
- stebakkabupaten" Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/tebakkabupaten.json
- Tebakkata" Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/tebakkata.json
- stebakkimia" Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/tebakkimia.json
- stebaklirik" Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/tebaklirik.json
- tebaktebakan" Quelle: https://raw.githubusercontent.com/BochilTeam/database/master/games/tebaktebakan.json
- Quelle "tekateki": https://raw.githubusercontent.com/BochilTeam/database/master/games/tekateki.json


### Nachrichten
```js
// Nachrichten
importieren {
    cnbindonesia,
    antaranews,
    kompas
} von '@bochilteam/scraper'
// Cnbindonesien
console.log(await cnbindonesia())
// Antaranews
console.log(await antaranews())
// Kompas
console.log(await kompas())
```
- antaranews" verwendet die Website https://www.antaranews.com
- `cnbindonesia` verwendet die Website https://www.cnbcindonesia.com
- Kompas" verwendet die Website https://www.kompas.com
- `liputan6` verwendet die Website https://www.liputan6.com
- merdeka" nutzt die Website https://www.merdeka.com
- suaracom` nutzen die Website https://www.suara.com

### Verschlüsselung
``js
// Verschlüsselung
importieren {
    toBase64,
    fromBase64ToString,
    randomUUID,
    randomBytes,
    createHash
} from '@bochilteam/scraper'
// Nach base64
const base64 = toBase64('Hallo Welt!!')
console.log(base64)
// Von base64 zu String
console.log(fromBase64ToString(base64)) // 'Hallo Welt!!'
// Zufällige UUID
console.log(randomUUID())
// Zufällige Bytes
console.log(randomBytes(16))
// Hash
console.log(createHash('sha256', 'Hallo Welt!!'))
```
- `randomUUID` Quelle: https://github.com/uuidjs/uuid/blob/main/src/v4.js und https://github.com/nodejs/node/blob/master/lib/internal/crypto/random.js
- `randomBytes` verwenden `crypto` Modul
- `createHash` benutze `crypto` Modul

### Bioskop
``js
// Bioskop
importieren {
    bioskopNow,
    bioskop
} von '@bochilteam/scraper'
// Bioskop 
console.log(await bioskop())
// Bioskop Jetzt
console.log(await bioskopNow())
```
- `bioskop` use website https://jadwalnonton.com
- `bioskopNow` use website https://jadwalnonton.com

### Downloader 
```js
importieren {
    mediafiredl,
    sfilemobi,
    sfilemobiSearch,
    zippyshare
} von '@bochilteam/scraper'
// Mediafire
console.log(await mediafiredl('https://www.mediafire.com/file/gpeiucmm1xo6ln0/hello_world.mp4/file'))
// Sfilemobi
console.log(await sfilemobi('https://sfile.mobi/oGm8kAIQCs7'))
// Sfilemobi Suche
console.log(await sfilemobiSearch('minecraft'))
// Zippyshare
console.log(await zippyshare('https://www53.zippyshare.com/v/Gajlfjd4/file.html'))
```
- `mediafiredl` benutze Website https://www.mediafire.com
- `sfilemobi` verwendet die Website https://www.sfilemobi.com
- `sfilemobiSearch` verwendet die Website https://www.sfilemobi.com
- `zippyshare` verwendet die Website https://www.zippyshare.com

### Akkord 
`js
importieren {
    chord
} von '@bochilteam/scraper'
// Akkord
console.log(await chord('Until i found you'))
```
- chord` use website https://www.gitagram.com

## Breaking Changes
### - von v2.0.0 auf v3.0.0
- `savefrom` gibt jetzt Array von Objekt statt Objekt aus
- `asmaulhusna` kann optional den Parameter `index` annehmen, um die asmaulhusna dieses Indexes zu erhalten (Standard ist random 1-99)
