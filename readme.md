# MarkdownTranslator
[[عربي]](readme.ar.md)

Alusus library for translating from Markdown to HTML.

## Usage

* Add the library to the project:

```
import "Apm";
Apm.importFile("Alusus/MarkdownTranslator");
```

* Instantiate the class:

```
def translator: MarkdownTranslator;
```

* Convert from MD to HTML:

```
htmlString = translator.translate(markdownString);
```

The `translate` method takes s `String` and returns a `String`.

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

