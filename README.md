# Coding standards
When contributing code to with me, you must follow its coding standards.

## Globális irányelvek

* [EditorConfig](http://editorconfig.org/) használata javasolt
* identre 4 space használata tabok helyett
* UTF-8 kódolás használata

## Frontend Coding Standards
*Frontend kódolási koncenciók*

### Alapvetések

* projekt indulásnál a [starter-kit](https://github.com/StarZ3r0/starter-kit) használatos
* törekedni kell a szemantikus kódra, a valid markup cél, de nem elvárás
* kizárólag HTML5 doctype használható
* kiemelt szempont a sebesség
* elvárt a böngészőfüggetlen kód, ha arról a specifikáció másképp nem rendelkezik, akkor a támogatott böngészők az Internet Explorer 10+, illetve a Chrome és Firefox legfrisebb verziói
* ha nem megoldható a böngészőfüggetlen kód, akkor törekedni kell az érintett böngészőben való használhatóságra

### HTML

* kötelező a HTML5 doctype (`<!doctype html>`)
* kötelező az UTF-8 kódolás (`<meta charset="UTF-8">`)
* self closing elemeknél tilos kitenni a záró perjelet (`<img src="/logo.png" alt="">`)

## PHP Coding Standards
*PHP kódolási koncenciók.*

* [PSR-1](http://www.php-fig.org/psr/psr-1/) és [PSR-2](http://www.php-fig.org/psr/psr-2/) követése
* Kommentek esetében a [phpDocumentor](http://www.phpdoc.org/docs/latest/index.html) előírásait kell követni

### Megjegyzések

* sorvégek Unix LF formában
* minden fájl végén legyen egy üres sor
* a <code>null</code>, továbbá a <code>true</code> és <code>false</code> kisbetűvel

### Kiegészítések

* short tag-ek használata tilos
* kód kommentelése elvárt a szükséges mértékben
* todo címkék használata lehetséges, de legyen felvive az Issue trackerbe

## Hasznos linkek

* [Isobar Front-end Code Standards](https://isobar-idev.github.io/code-standards/)
