# AMP Translations

AMP 2.2.1.0 and newer support localisation through the use of a locale file that has the various AMP messages in different languages. These are accessible so that anyone can contribute new languages or collaborate on existing ones.

Note: At time of writing, you'll need to use the Nightly AMP build to get this functionality as 2.2.1.0 has not yet been released.

## Building Translation Files

Under `WebRoot/Locale` you'll find a file called `xx.json` that shows you the structure of the language file. A copy of this also exists in this repo.

Duplicate this file, and rename it to the appropriate two-letter [ISO 639-1 code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) for the language you're working on (e.g. `de.json` for German.

Under the 'Strings' object, there is a key for each original text node in English, followed by its translation in whatever language you chose. You'll also need to replace the `LocaleName` object to match the ISO 639-1 code, and update the `MonthsOfYear`, `DaysOfWeek` and `LongDaysOfWeek` arrays to have the months and days in your target language.

Any strings within AMP that don't exist in your translation file will remain as English, so you can work on it gradually over time.

## Testing your translation

Place your new `.json` file in the `WebRoot/Locale` directory, then navigate to your AMP installation with `?lang=xx` at the end of the URL, with `xx` corresponding to the ISO 639-1 code for your file. E.g. `https://panel.example.com/?lang=de` - AMP will then load this language file. You can revert back to English by using `?lang=en`.

Be mindful of spacing and layout, AMP should accomodate things just fine - but in some circumstances you may need to be a little creative to make things fit. If there's some element of AMP that really isn't responding well to a change then let us know and we'll look at how it can be addressed.

## Contributing Translation Files

You can contribute new translations by making a pull request here on Github. We will review them and offer other community members a chance to vet them for quality. Translations that are deemed to be high quality and accurate may be accepted into AMP itself.

You can collaborate on or make suggestions for alterations or improvements in the same way. We encourage you to make use of the comments on pull requests if you feel something could be done better.

Be aware that by contributing a translation that you are giving us permission to include it in our commercially distributed software.

Also be mindful that AMP has many different modules and plugins, you may want to try out your translation in a few different games. AMP re-applies translations for loaded tabs after login.

## Esoteric Translations

If you're planning on submitting an esoteric translation such as Pirate, please use the format of `xxname.json` and `xxname` as the locale. E.g. `xxpirate.json` and `"LocalName": "xxpirate"` to denote that they are not serious translations.
