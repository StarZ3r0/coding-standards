# Coding standards
When contributing code to with me, you must follow its coding standards.

## Globális irányelvek

* verziószámozás esetében a [Semantic Versioning](http://semver.org/) követendő
* [EditorConfig](http://editorconfig.org/) használata javasolt
* changelog (`changelog.md`) készítése javasolt a [Keep a Changelog](http://keepachangelog.com/en/0.3.0/) ajánlásai alapján
* identre 4 space használata tabok helyett
* UTF-8 kódolás használata
* minden fájlnév kisbetűs, szavak elválasztására kötöjelet (`-`) kell használni
* a kód dokumentálása történhet magyar vagy angol nyelven, viszont fontos, hogy konzekvens legyen

## UX

Nyelvek megjelenítésére vonatkozó ajánlások többnyelvű oldalak esetén ([további információ](http://www.flagsarenotlanguages.com/blog/best-practice-for-presenting-languages/)):
- a felhasználó saját nyelvén legyen megjelenítve a nyelv (pl. german helyett deutsch)
- lehetőség szerint az összes elérhető nyelvet jelenítsük meg
- detektáljuk a felhasználó böngészőjének a nyelvét
- ne használjunk zászlókat a nyelvek reprezentálására

## Frontend Coding Standards
*Frontend kódolási koncenciók*

### Alapvetések

* projekt indulásnál a [starter-kit](https://github.com/StarZ3r0/starter-kit) használatos
* törekedni kell a szemantikus kódra, a valid markup cél, de nem elvárás
* kiemelt szempont a sebesség
* elvárt a böngészőfüggetlen kód, ha arról a specifikáció másképp nem rendelkezik, akkor a támogatott böngészők az Internet Explorer 10+, illetve a Chrome és Firefox legfrisebb verziói
* ha nem megoldható a böngészőfüggetlen kód, akkor törekedni kell az érintett böngészőben való használhatóságra

### HTML

* kizárólag kisbetűket használunk
* célszerű használni a HTML5 szemantikus új elemeit (header, footer, nav, article, section, stb...)
* kizárólag HTML5 doctype használható (`<!doctype html>`)
* kötelező az UTF-8 kódolást jelölő meta tag (`<meta charset="UTF-8">`), a kódolás megadásának az első [1024 byteban](http://www.whatwg.org/specs/web-apps/current-work/multipage/semantics.html#charset) kell lennie
* self closing elemeknél tilos kitenni a záró perjelet (`<img src="/logo.png" alt="">`)
* attribútumok értékeinél double quotes használatos (`"`)
* entitásokat nem használunk, a kivételes eseteket leszámítva (`<` és `>`, illetve `&` némelyik speciális vezérlőkarakterhez, mint pl. a nem törhető szóközhöz)

### CSS

* kizárólag kisbetűket használunk
* az egyes definíciók közé üres sor rakunk
* id- és osztályneveknél a szavak elválasztására kötőjelet használunk (`.button-large`)
* a tulajdonságokat záró kettőspont utánt szóközt teszünk (`font-weight: bold;`)
* url-ek megadásánál aposztrófot használunk (url('/image.png'))
* `!important` kulcsszó használata kerülendő

Példa:
```
html {
    background: #fff;
}

.post-meta {
    margin: auto;
    width: 50%;
}
```

### JavaSrcipt

* JS prefix használata ajánlott, ezek formázása CSS-el kerülendő
```
<div id="js-slider" class="my-slider">
```
* kód dokumentálásához a [JSDoc](http://usejsdoc.org/) használandó

### Assetek

* képek fájlneveiben kötőjelet használunk (`header-background.png`)

## PHP Coding Standards
*PHP kódolási koncenciók.*

* [PSR-1](http://www.php-fig.org/psr/psr-1/) és [PSR-2](http://www.php-fig.org/psr/psr-2/) követése
* sztringek esetében az idézőjel (`"`) használata kötelező
* Kommentek esetében a [phpDocumentor](http://www.phpdoc.org/docs/latest/index.html) előírásait kell követni
* vezérlési szerkezeteknél használhatóak az [alternatív verziók](http://php.net/manual/pl/control-structures.alternative-syntax.php), mint például az `endif` és `endforaech`, de főleg templatekben

Short if használata (a váratlan eredmények elkerülése érdekében):
```
$error = ($error_status ? 'Error' : 'No Error');
```
Sztringek összefűzésénél:
```
$error = 'Status: ' . ($error_status ? 'Error' : 'No Error');
```
* short tag-et lehet használni és nem szükséges a végére pontosvessző ([forrás](http://php.net/manual/en/language.basic-syntax.instruction-separation.php))
```
<?= $var ?>
```
* osztály példányosításakor kirakjuk a zárójelet
```
$car = new Car();
```

### Megjegyzések

* sorvégek Unix LF formában
* minden fájl végén legyen egy üres sor
* a <code>null</code>, továbbá a <code>true</code> és <code>false</code> kisbetűvel

### Kiegészítések

* short tag-ek használata tilos
* kód kommentelése elvárt a szükséges mértékben
* todo címkék használata lehetséges, de legyen felvive az Issue trackerbe

## Ajánlott külső függvénykönyvtárak

Az ajánlott vendorok megtalálhatóak az [awesome-links](https://github.com/StarZ3r0/awesome-links) gyűjteményemben.

## Hasznos linkek

* [Isobar Front-end Code Standards](https://isobar-idev.github.io/code-standards/)
* [Code Guide by @mdo](http://codeguide.co/)
