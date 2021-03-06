# markdown_cjk_spacing

Python markdown extension for insert a space between Chinese / Japanese /
Korean and English words, to display beautifully.

`中文Chinese西文English` is converted to `中文 Chinese 西文 English`.

![build](https://travis-ci.org/EloiseSeverin/markdown_cjk_spacing.svg?branch=master)

### Installation

Install with pip.

```
$ pip install markdown-cjk-spacing
```

### Usage

It is used as an extension of [Python-Markdown][].

```.python
import markdown

md = markdown.Markdown(extensions=["markdown_cjk_spacing.cjk_spacing"])
md.convert("markdown text")
```

Or use from [Pelican][] as Markdown extension.

```.python
# pelicanconf.py
MARKDOWN = {
    'extension_configs': {
        'markdown.extensions.codehilite': {'css_class': 'highlight'},
        'markdown.extensions.extra': {},
        'markdown.extensions.meta': {},
        'markdown_cjk_spacing.cjk_spacing': {},
    },
    'output_format': 'html5',
}
```

### Segment split conversion

In Chinese / Japanese sentences, if you do a line feed, it will be a one-byte space, but you can delete this space.

```.python
import markdown

md = markdown.Markdown(extensions=["markdown_cjk_spacing.cjk_spacing"],
    extension_configs={'markdown_cjk_spacing.cjk_spacing':
            {'segment_break': True}})
md.convert("markdown text")
```

[Python-Markdown]: https://github.com/Python-Markdown/markdown "Python-Markdown"
[Pelican]: https://blog.getpelican.com/ "Pelican Static Site Generator"
