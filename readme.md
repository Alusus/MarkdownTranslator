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

