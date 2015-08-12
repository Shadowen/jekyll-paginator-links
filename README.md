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

| CSS Selector                               | Component | Description |
| ------------------------------------------ | --------- | ----------- |
| `.paginator-links` |  | A wrapper for the entire generate set of links.
| `.paginator-links .start-ellipsis::before` |  | The `content` attribute is the text shown when page numbers have been truncated from the beginning of the list.
| `.paginator-links .end-ellipsis::before` |  | The `content` attribute is the text shown when page numbers have been truncated from the end of the list.
| `.paginator-links .seperator::before` |  | The characters to use as seperators between page numbers.
| `.paginator-links .first-page::before` |  | The `content` attribute is the text to use for the link to the first page. Styling should also be performed here. If blank, the "First Page" link will not be displayed.
| `.paginator-links .previous-page::before` |  |  The `content` attribute of this is the text to use for the link to the previous page. Styling should also be performed here. If blank, the "Previous Page" link will not be displayed.
| `.paginator-links .next-page::before` |  | The `content` attribute of this is the text to use for the link to the next page. Styling should also be performed here. If blank, the "Next Page" link will not be displayed.
| `.paginator-links .last-page::before` |  | The `content` attribute of this is the text to use for the link to the last page. Styling should also be performed here. If blank, the "Last Page" link will not be displayed.
| `.paginator-links .numbers` |  | A `div` wrapping directly around the all the numbers, but not the ellipses or navigation buttons.
| `.paginator-links .number` |  | The styling for each individual number.
| `.paginator-links a` |  | The actual hyperlink. `:link` and `:visited` pseudoclasses are useful here.
| `.paginator-links .number.current` |  | The currently selected page.

# Why `root`
Everything in this demo is in the root folder of the repository because of the way GitHub Pages renders project pages. Unfortunately there is no work-around for this. However, in user pages you may use any arbitrary directory, so `paginator-links.css` can be stored in the `css/` or `styles/` folder of your choice.

# Inspiration
- http://stackoverflow.com/questions/14025597/liquid-and-arithmetic
- http://stackoverflow.com/questions/27963027/jekyll-long-pagination-how-to-shorten-it
- http://stackoverflow.com/questions/30125878/can-i-have-a-proper-nice-tiled-pagination-in-jekyll-using-liquid-templates
