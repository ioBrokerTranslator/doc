This document contains information and guidelines for everybody who likes to contribute to ioBroker translations.

# Context

Many parts of ioBroker are translated into different languages. These include, but are not limited to:
- Core adapters like [ioBroker.admin](https://github.com/ioBroker/ioBroker.admin), [ioBroker.discovery](https://github.com/ioBroker/ioBroker.discovery), [ioBroker.info](https://github.com/ioBroker/ioBroker.info)
- Well over 300 community adapters
- Common tools
- Documentation

All those translations should be managed in the future through our own [Weblate](https://weblate.iobroker.net/) server.

**Important:** Anybody in the ioBroker community can contribute to translations. This is *not limited to developers*.

# Translating

## Login

Translation is done through our [Weblate](https://weblate.iobroker.net/) server. You can either log in with your GitHub account (if you own one), or you can create a new Weblate account manually.

## General Documentation

This document will not cover how Weblate works but rather concentrates on the specifics of translations for ioBroker.

For a general documentation, please refer to the [official Weblate documentation](https://docs.weblate.org/en/latest/user/translating.html).

If you have further questions, please don't hesitate to ask them in our [forum](https://forum.iobroker.net/), on [Discord](https://discord.com/invite/HwUCwsH) or in our dedicated [Telegram group](https://t.me/joinchat/RpbX0672BFw1MDg0).

## Structure

Weblate divides all translations into projects and components.

ioBroker currently has the following Weblate projects
- "ioBroker Adapters" contains all translations of adapters independent of their origin
- "ioBroker Tools" contains all tools that are translated into multiple languages

Each component is translated into different languages. Currently we support the following languages:
- English (en)
- German (de)
- Dutch (nl)
- French (fr)
- Italian (it)
- Polish (pl)
- Portuguese (pt)
- Russian (ru)
- Spanish (es)
- Simplified Chinese (zh_Hans)
- Ukrainian (uk)

## Process

Weblate is directly connected to the developer's GitHub repository. This allows us to:
- immediately get new strings from the repository into Weblate and 
- automatically create pull requests in the respective GitHub repository for updated translations.

After three (3) hours, translations will be uploaded from Weblate to GitHub.

Developers create new strings by adding them to a file (usually called something like `en.json` or `en/translations.json`). Then those strings are automatically translated to all other languages using Google Translate.

As a translator, you can simply go through "your" language and start reviewing the available automatic translations.

### Colors

Strings are marked with different colors. They have the following meaning:
- Dark green: Read only strings - are locked for translation because the original English translation must be reviewed first
- Green: Translated strings - these strings were reviewed before and usually don't need to be changed (unless you find an error)
- Dark orange: Strings needing action (and others) - these strings need to be reviewed and if necessary updated
- Yellow: Failed checks (and others) - there are warnings about those strings, have a look at them and fix them if you can

# General Guidelines

The following guidelines are valid for all translations.

### Have a Look at the Current Translation in ioBroker

Before editing a string, it might be a good idea to install the given adapter and have a look at how the string is used. This might help you find the right wording.

If you don't find the string, don't hesitate to search in the code (most of the time, you'll find the "key" somewhere in the code) or ask the original developer.

### Keep the same Language

Google Translate has the tendency to translate the same term differently depending on the sentence it is used in.

Please try to use the same language everywhere (see also the next two sections).
If you are unsure, don't hesitate to look how a term is translated in other adapters or even ask in the forum/Discord.

### Use ioBroker Specific Terms

ioBroker has some very specific terms that should always be translated the same way (including in English).
Often you can find them in the [glossary in Weblate](https://weblate.iobroker.net/glossaries/adapters/); if a specific term is missing, feel free to add it to the glossary.

Examples are:
- Adapter
- Binding
- Channel
- Controller
- Device
- IP Address
- Port
- State

### Use Technology Specific Terms

When translating an adapter for a given technology, please make sure to use the words in your language that are "native" to the given technology.
Google Translate doesn't know about the context of these words and thus translates them wrongly.
If neccessary, have a look for example at the user manual (unless of course it was itself translated with Google Translate ;-).

### Keep all Placeholders

If the English text has placeholders (e.g. `%s` or `$xyz` or similar), make sure they are in the right position for your language.

Example:
- Original: `Deleted %s states`
- German: `%s Datenpunkte wurden gelöscht` (notice the `%s` moving to the front of the sentence)

### Keep all Formatting Characters/Tags

If the English text contains formatting charcters or HTML tags, try to keep them in the same place for your language.

### Keep the Same Punctuation

Terminate all complete sentences with the correct punctuation - most likely a dot.

If the English text has punctuation (especially at the end of the string) make sure, you keep them - but of course adjust them to your language.

Examples:
- Original: `How do you want to configure this adapter?`
- German: `Wie soll dieser Adapter konfiguriert werden?`
- French: `Comment cet adaptateur doit-il être configuré ?` (notice the space before the question mark as this is the way questions are usually written in French)
- Spanish: `¿Cómo desea configurar este adaptador?` (notice the the `¿` in front of the question as it is done in Spanish)

### Keep a Similar Length

It is not always possible, but try to keep a similar length for the translated strings.

For example a one-word string might be used as a column header; if you translate it now with a three-words string, the column might accidentally get bigger than the developer anticipated.

### Labels Should Start With a Capital Letter

Labels should always start with a capital letter whether it is a noun or not.

# Language Specific Guidelines

The following guidelines are specific for each language strings are translated **to**. They are written in the respective language as this makes them easier understandable.

## Deutsch

### Unpersönliche Form

Es soll immer die "unpersönliche" Form verwendet werden. Beispiel:
- Original: You must provide a username and password.
- Richtig: Bitte Benutzername und Passwort angeben.
- Falsch: ~Du musst Benutzername und Passwort angeben.~
- Falsch: ~Sie müssen Benutzername und Passwort angeben.~

Damit verhindern wir, dass wir uns zwischen Duzen und Siezen entscheiden müssen und verkürzen auch manchmal die Texte.

