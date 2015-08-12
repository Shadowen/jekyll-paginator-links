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

# Why `root`
Everything in this demo is in the root folder of the repository because of the way GitHub Pages renders project pages. Unfortunately there is no work-around for this. However, in user pages you may use any arbitrary directory, so `paginator-links.css` can be stored in the `css/` or `styles/` folder of your choice.

# Inspiration
- http://stackoverflow.com/questions/14025597/liquid-and-arithmetic
- http://stackoverflow.com/questions/27963027/jekyll-long-pagination-how-to-shorten-it
- http://stackoverflow.com/questions/30125878/can-i-have-a-proper-nice-tiled-pagination-in-jekyll-using-liquid-templates
