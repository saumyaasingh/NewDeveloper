# SignIt
**Lingua Libre SignIt** translate a word in (French) Sign Language videos.
## what is done exactly?
This extension allows you to translate a word into French sign language on any web page. When you read a text and come across a word you don't know, highlight that word, right click and click on the Sign it icon: the sign in LSF and the definition of the word in French will appear on a window. If a word is not available in LSF, we invite you to record it with our easy-to-use webapp on https://lingualibre.org. The definitions come from the French Wiktionary to which you can also contribute: https://fr.wiktionary.org.

## Install
* Firefox > Open: https://addons.mozilla.org/en-US/firefox/addon/lingua-libre-signit/ > Install.

Manual install is possible for Chrome, Chromium. Should be eqully possible with Windows Edge.

## Build & hack

```
# git clone the repository first, then...
npm install                 # Install dependencies
# Bump version in package.json and manifest.json, ex: 1.0.12 -> 1.0.13
npm run web-ext:build       # build the firefox extension into an instalable .zip
npm run web-ext:test        # runs current dev version in Firefox, opens url defined in package.json
```
See also [Mozilla's web-ext](https://github.com/mozilla/web-ext)

[Inspect Firefox extension](https://extensionworkshop.com/documentation/develop/debugging/) : Open url `about:debugging#/runtime/this-firefox`.
There, `Load temporary Add-on`, find "Lingua Libre SignIt" : click `Inspect`.

## Visuals
<img src="doc/LinguaLibre_SignIt-01.png"/>
<img src="doc/LinguaLibre_SignIt-all.png"/>

## Development
```
├── manifest.json (v.2) — defines extensions and dependencies rights.
├── background-script.js — main script.
├── SignItCoreContent.js — creates duo panels "Video | Definition"
├── SignItVideosGallery.js — given urls, creates gallery of videos.
├── content_scripts/
|   ├── signit.js — creates above text SignIt popup
|   └── wpintegration.js — on wikimedia sites, if page's title has a sign language video available, then display smartly.
└── popup/
    ├── popup.js — creates top bar SignIt icon's popup, with search, history and settings.
    └── SearchWidget.js — handle the search queries
```

## Contribute
### Contributors
We look for volunteers:
* Co-owners, JS developers
* Signers

### Contact
* [hugolpz](https://github.com/hugolpz)

### Code
- [Github: Lingua-libre/SignIt/Issues](https://github.com/lingua-libre/SignIt/issues) — tickets manager
- [Github: Lingua-libre/SignIt](https://github.com/lingua-libre/SignIt) — code (JS)
- [Translate SignIt's user interface](https://translatewiki.net/wiki/Translating:Lingua_Libre_SignIt)

## Documentation
* [:meta:Lingua Libre/SignIt](https://meta.wikimedia.org/wiki/Lingua_Libre/SignIt) — Wikimedia project page with mission statement.

## Services
* [Lingualibre.org > Recording Studio](https://LinguaLibre.org/wiki/Special:RecordWizard) — online tool to record words, once you specify a sign language, you can record videos of signed word at 400 per hour. They will be automatically available to SignIt.
* [Lingua Libre SignIt for Firefox](https://addons.mozilla.org/en-US/firefox/addon/lingua-libre-signit/) — a browser extension to click words in browser and show sign language videos generated via Lingualibre.
