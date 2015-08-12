Works together with [Jekyll's Pagination](http://jekyllrb.com/docs/pagination/) function to generate a list of links to pages.

# [Live demo](http://shadowen.github.io/jekyll-paginator-links/)

# Usage
1. In your `_config.yml`, add the line:

  ```yaml
  paginate: 5
  ```
  Note the number you set here is the number of posts/page.
2. Copy [`_includes/paginator-links.html`](https://raw.githubusercontent.com/Shadowen/jekyll-paginator-links/gh-pages/_includes/paginator-links.html) to your own `_includes/` folder.
3. Copy [`paginator-links.css`](https://raw.githubusercontent.com/Shadowen/jekyll-paginator-links/gh-pages/paginator-links.css) to your own root folder. (See [below](#why-root))
  - Customize this CSS file later to change the look and feel of your links!
4. In your `index.html` (or wherever you're paginating), paste the following segment:

  ```liquid
  <style>{% include paginator-links.css %}</style>
  {% include paginator-links.html maxPages=5 %}
  ```

# Customizing
Some useful selectors to use in the stylesheet `paginator-links.css`.

| CSS Selector | Component | Description |
| ------------------------------------------ | --------- | ----------- |
| `.paginator-links` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231716/a9a98080-40f7-11e5-95f5-37adf0da9e5d.png) | A wrapper for the entire generate set of links. |
| `.paginator-links .start-ellipsis::before` | ![image](https://cloud.githubusercontent.com/assets/8551479/9232101/bbf1b97c-40f9-11e5-8eeb-886a337f1138.png) | The `content` attribute is the text shown when page numbers have been truncated from the beginning of the list. |
| `.paginator-links .end-ellipsis::before` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231951/01eb42b4-40f9-11e5-9438-20b7b49bca4f.png) | The `content` attribute is the text shown when page numbers have been truncated from the end of the list. |
| `.paginator-links .seperator::before` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231893/a164b6e6-40f8-11e5-8837-424dd4516d85.png) | The characters to use as seperators between page numbers. |
| `.paginator-links .first-page::before` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231744/d9d8411a-40f7-11e5-8164-ac27a42ac71f.png) | The `content` attribute is the text to use for the link to the first page. Styling should also be performed here. If blank, the "First Page" link will not be displayed. |
| `.paginator-links .previous-page::before` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231770/fc8d67e4-40f7-11e5-98c5-6135b952c97b.png) |  The `content` attribute of this is the text to use for the link to the previous page. Styling should also be performed here. If blank, the "Previous Page" link will not be displayed. |
| `.paginator-links .next-page::before` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231970/1e14d860-40f9-11e5-90ac-bf1cfcff7075.png) | The `content` attribute of this is the text to use for the link to the next page. Styling should also be performed here. If blank, the "Next Page" link will not be displayed. |
| `.paginator-links .last-page::before` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231993/3998961c-40f9-11e5-926b-734f36e39e0f.png) | The `content` attribute of this is the text to use for the link to the last page. Styling should also be performed here. If blank, the "Last Page" link will not be displayed. |
| `.paginator-links .numbers` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231796/278fa254-40f8-11e5-8f8d-be4e812c213c.png) | A `div` wrapping directly around the all the numbers, but not the ellipses or navigation buttons. |
| `.paginator-links .number` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231921/cdcbc03a-40f8-11e5-8c45-8a343298d4bb.png) | The styling for each individual number. |
| `.paginator-links a` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231921/cdcbc03a-40f8-11e5-8c45-8a343298d4bb.png) | The actual hyperlink. `:link` and `:visited` pseudoclasses are useful here. |
| `.paginator-links .number.current` | ![image](https://cloud.githubusercontent.com/assets/8551479/9231881/8d2089a8-40f8-11e5-8fc4-441bb5828d7d.png) | The currently selected page. |

# Why `root`
Everything in this demo is in the root folder of the repository because of the way GitHub Pages renders project pages. Unfortunately there is no work-around for this. However, in user pages you may use any arbitrary directory, so `paginator-links.css` can be stored in the `css/` or `styles/` folder of your choice.

# Inspiration
- http://stackoverflow.com/questions/14025597/liquid-and-arithmetic
- http://stackoverflow.com/questions/27963027/jekyll-long-pagination-how-to-shorten-it
- http://stackoverflow.com/questions/30125878/can-i-have-a-proper-nice-tiled-pagination-in-jekyll-using-liquid-templates
