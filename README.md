# Humanizer
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE.md) [![Build Status](https://travis-ci.org/sbani/go-humanizer.svg?branch=master)](https://travis-ci.org/sbani/go-humanizer) [![GoDoc](https://godoc.org/github.com/sbani/go-humanizer?status.svg)](https://godoc.org/github.com/sbani/go-humanizer)

Humanize values to make them easier to read.

## Installation
```bash
go get github.com/sbani/go-humanizer
```

## Usage
### Strings
#### Humanize:
```go
import "github.com/sbani/go-humanizer/strings"

Humanize("news_count", true) // "News count"
Humanize("User", false) // "user"
Humanize("news_id", true) // "News"
```
#### Truncate:
Truncate string but never cut within a word.
```go
import "github.com/sbani/go-humanizer/strings"

textShort := "Short text"
Truncate(textShort, 1) // Short
Truncate(textShort, 6) // Short
Truncate(textShort, 7) // Short text
```
### Numbers
#### Ordinalize:
```go
import "github.com/sbani/go-humanizer/numbers"

Ordinalize(0) // "0th"
Ordinalize(1) // "1st"
Ordinalize(2) // "2nd"
Ordinalize(23) // "23rd"
Ordinalize(1002) // "1002nd"
Ordinalize(-111) // "-111th"
```
#### Ordinal:
```go
import "github.com/sbani/go-humanizer/numbers"

Ordinal(0) // "th"
Ordinal(1) // "st"
Ordinal(2) // "nd"
Ordinal(23) // "rd"
Ordinal(1002) // "nd"
Ordinal(-111) // "th"
```
#### Roman:
```go
import "github.com/sbani/go-humanizer/numbers"

ToRoman(1) // "I"
ToRoman(5) // "V"
ToRoman(1300) // "MCCC"

FromRoman("MMMCMXCIX") // 3999
FromRoman("V") // 5
FromRoman("CXXV") // 125
```
### Collection
#### Oxford
```go
import "github.com/sbani/go-humanizer/collection"

Oxford([]string{"Albert"}, -1) // "Albert"
Oxford([]string{"Albert", "Norbert"}, -1) // "Albert and Norbert"
Oxford([]string{"Albert", "Norbert", "Michael", "Kevin"}, -1) // "Albert, Norbert, Michael and Kevin"
Oxford([]string{"Albert", "Norbert", "Michael", "Kevin"}, 2)) // Albert, Norbert and 2 more
```

## License
MIT License. See LICENSE file for more informations.

## Credits
A special WOW goes to [PHP Humanizer](https://github.com/coduo/php-humanizer). (This lib is just a port)

## Contributions
Contributions are very welcome! Feel free to contact me, send a PR or open an issue.

## Roadmap
Things that are missing:
- [x] Strings: Humanize
- [x] Strings: Truncate
- [x] Numbers: Roman
- [x] Numbers: Ordinal
- [x] Collection: Oxford
- [ ] Numbers: Binary Suffix
- [ ] Numbers: Metric Suffix
- [ ] Date time: Difference
- [ ] Date time: Precise difference
- [ ] Translations
