# MarkdownTranslator
[[English]](readme.md)

مكتبة للغة الأسس للتحويل من صيغة ماركداون إلى صيغة HTML.

## الاستخدام

* أضف المكتبة للمشروع:

<div dir=rtl>

```
اشمل "مـحا"؛
مـحا.اشمل_ملف("Alusus/MarkdownTranslator"، "مـترجم_ماركداون.أسس")؛
```

</div>

```
import "Apm";
Apm.importFile("Alusus/MarkdownTranslator");
```

* أنشئ متغيرا من صنف المترجم:

<div dir=rtl>

```
عرف مترجم: مـترجم_ماركداون؛
```

</div>

```
def translator: MarkdownTranslator;
```

* حول من صيغة ماركداون إلى HTML:

<div dir=rtl>

```
نص_إتش_ت_م_ل = مترجم.ترجم(نص_ماركداون)؛
```

</div>

```
htmlString = translator.translate(markdownString);
```

دالة `ترجم` تستلم `نـص` وترجع `نـص`.

