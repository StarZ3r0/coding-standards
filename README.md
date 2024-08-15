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
* hibák jezése az [alábbi útmutató](https://www.perfectbugreport.io/) alapján

### HTML

* kizárólag kisbetűket használunk
* célszerű használni a HTML5 szemantikus új elemeit (header, footer, nav, article, section, stb...)

Példa: új komponens esetében használjuk a `<section>` vagy az `<article>` elemeket:
```html
<section class="component">
  <h1 class="title">Title</h1>
  <p>Paragraph</p>
</section>
```

* kizárólag HTML5 doctype használható (`<!doctype html>`)
* kötelező az UTF-8 kódolást jelölő meta tag (`<meta charset="UTF-8">`), a kódolás megadásának az első [1024 byteban](http://www.whatwg.org/specs/web-apps/current-work/multipage/semantics.html#charset) kell lennie
* self closing elemeknél tilos kitenni a záró perjelet (`<img src="/logo.png" alt="">`)
* attribútumok értékeinél double quotes használatos (`"`) [w3c](https://www.w3.org/TR/html4/intro/sgmltut.html#h-3.2.2)
* attribútumok sorrendje a [codeguide](https://codeguide.co/) szerint
* entitásokat nem használunk, a kivételes eseteket leszámítva (`<` és `>`, illetve `&` némelyik speciális vezérlőkarakterhez, mint pl. a nem törhető szóközhöz)

### CSS

* kizárólag kisbetűket használunk
* az egyes definíciók közé üres sor rakunk
* minden deklaráció kerüljön új sorba
* id- és osztályneveknél a szavak elválasztására kötőjelet használunk (`.button-large`)
* a tulajdonságokat záró kettőspont utánt szóközt teszünk (`font-weight: bold;`)
* url-ek megadásánál aposztrófot használunk (url('/image.png'))
* preferáltan az osztályokat hasznájuk leginkább
* ajánlott maximum 3 szint mélységig menni az osztályok [specificity](https://specificity.keegan.st/)-jében
* `!important` kulcsszó használata kerülendő
* shorthand-ek felesleges használata kerülendő, pl. ne használjunk ```background``` shorthandet ha csak háttérszínt szeretnék módosítani
* ha valahol elkerülhetetlen a CSS hack használata, akkor különítsül el egy shame.css-be
* 0, mint érték megadása esetén a mértékegység megadása felesleges ezért kerülendő

Példa:
```css
html {
    background: #fff;
}

.doc-block,
.post-meta {
    margin: auto;
    width: 50%;
}

.navbar {
  margin-bottom: var(--space);

  @media (min-width: 480px) {
    padding: 10px;
  }

  @media (min-width: 768px) {
    position: absolute;
    top: 0;
    left: 0;
  }

  @media (min-width: 992px) {
    position: fixed;
  }
}
```

### JavaSrcipt

* JS prefix használata ajánlott, ezek formázása CSS-el kerülendő
```html
<div id="js-slider" class="my-slider">
```
* kód dokumentálásához a [JSDoc](http://usejsdoc.org/) használandó

### Assetek

* képek fájlneveiben kötőjelet használunk (`header-background.png`)

## PHP Coding Standards
*PHP kódolási koncenciók.*

* változónevek kiválaszátáshoz a [naming-cheatsheet](https://github.com/kettanaito/naming-cheatsheet)-et ajánlott alkalmazni
* [PSR-1](http://www.php-fig.org/psr/psr-1/) és [PSR-12](http://www.php-fig.org/psr/psr-12/) követése
* sztringek esetében az aposztróf (`'`) használata kötelező, változók esetében használható a double quote (```"```)
```php
$q = htmlentities($searchValue, ENT_QUOTES, 'UTF-8');
echo "<input type='search' name='q' placeholder='Search' value='$q'>";
```

* Kommentek esetében a [phpDocumentor](http://www.phpdoc.org/docs/latest/index.html) előírásait kell követni
* vezérlési szerkezeteknél használhatóak az [alternatív verziók](https://www.php.net/manual/en/control-structures.alternative-syntax.php), mint például az `endif` és `endforaech`, de főleg templatekben

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

### Eszközök

* statikus kód analízis

### Kiegészítések

* short tag-ek használata tilos
* kód kommentelése elvárt a szükséges mértékben
* todo címkék használata lehetséges, de legyen felvive az Issue trackerbe

## Laravel specifikus

### Alapvetések

* [Laravel Best Practices](https://github.com/alexeymezenin/laravel-best-practices)-ban leírt ajánlások követése

### Frissítés

* Adott projekt abban a verzióban tölti a teljes életciklusát, amelyben indult
* Nagyobb és folyamatosan karbantartott projektek esetében [Laravel Shift](https://laravelshift.com/)-el (vagy manuálisan) frissítünk

## Git

* a [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) szerint
* használt commit típusok
```
feature
bugfix
task
wip
```
Példák:
```
git commit -m "feat: allow provided config object to extend configs"
git commit -m "docs: correct spelling of CHANGELOG"
git commit -m "feat(lang): add the Portuguese language"
```

## Tartalom

* ha a projekt költségvetés engedi, akkor érdemes szövegírót alkalmazni
* ha az előbbira nincs lehetőség, akkor a [közérthető fogalmazás](https://kozerthetofogalmazas.hu/) alapelveit érdemes betartani

## Ajánlott külső függvénykönyvtárak

Az ajánlott vendorok megtalálhatóak az [awesome-links](https://github.com/StarZ3r0/awesome-links) gyűjteményemben.

## Hasznos linkek

* [W3C Markup Validation Service](https://validator.w3.org/)
* [HTML5 Boilerplate](https://github.com/h5bp/html5-boilerplate)
* [Isobar Front-end Code Standards](https://isobar-idev.github.io/code-standards/)
* [Code Guide by @mdo](http://codeguide.co/)
* [HTML Best Practices](https://github.com/hail2u/html-best-practices)
* [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
