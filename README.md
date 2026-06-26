# MarkdownTranslator

[[عربي]](README.ar.md)

Alusus library for translating from Markdown to HTML.

## Usage

* Add the library to the project:

```
import "Apm";
Apm.importPackage("Alusus/MarkdownTranslator@0.1");
```

* Instantiate the class:

```
def translator: MarkdownTranslator[Regex.Matcher];
```

* Convert from MD to HTML:

```
htmlString = translator.translate(markdownString);
```

The `translate` method takes s `String` and returns a `String`.

### Template Arguments

`MarkdownTranslator` accepts two template arguments:

* `RegexType: type`
  The regex engine type to use for pattern matching.

* `USE_POSIX_REGEX: integer = 0`
  When set to `1`, switches the regex patterns for links, images, and general text to
  POSIX-compatible variants. Use this when the regex engine you are providing requires
  POSIX ERE syntax (e.g. it does not support `\x5D` hex escapes for `]`). Defaults to `0`
  (non-POSIX patterns).

Example:

```
def translator: MarkdownTranslator[Regex.Matcher, 1];
```

### onHtmlTag Function

You can control the creation of HTML tags by setting the onHtmlTag closure, which receives 3 arguments:

* tag: CharsPtr
  A string specifying the type of HTML tag being created. For example: h1.

* sourceText1: String.
  A string containing the original text extracted from the MD file. This won't include markdown special
  characters, like #.

* sourceText2: String.
  The second text extracted from the MD file for elements that has two pieces of text info, like anchor
  elements which has a label and a URL.

The closure should return a string, which is the generated HTML tag. If it returns an empty string then
MarkdownTranslator will generate the HTML tag itself.

## License

Copyright (C) 2026 Sarmad Abdullah

This project is licensed under the GNU Lesser General Public License v3.0 (LGPL-3.0). See the `COPYING` and `COPYING.LESSER` files for details.

