Introduction
============

This package provides reusable tiles based on plone.app.tiles.

At the time of writing you need checkouts

  * plone.app.blocks
  * plone.app.tiles
  * plone.tiles

Just add to your sources part for mr.developer auto-checkout:

```
[sources]
...
# Additional plone checkouts
plone.app.blocks            = git https://github.com/plone/plone.app.blocks.git
plone.app.tiles             = git https://github.com/plone/plone.app.tiles.git
plone.tiles                 = git https://github.com/plone/plone.tiles.git
```

A custom css file and the required javascript scaffolding is installed and
registered that enables using tiles by simply including a snippet in your
template:

```
<div tal:attributes="data-tile string:${context/absolute_url}/@@kk.tiles.richtext/mytile" />
```

where you can replace "mytile" with the actual name of the content block you
would like to make editable.


Note:
-----

In order to use the overlay editing capabilities with plone.app.theming you
should include a "minimal.html" stripped down to the bare basics. Since the
tiles overlay renders an iframe the contents of the overlay are better left
as basic styled.

In order to enable the basic template in your theme use:

```
<theme href="minimal.html" if-path="@@edit-tile" />
```
