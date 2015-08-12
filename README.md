Works together with [Jekyll's Pagination](http://jekyllrb.com/docs/pagination/) function to generate a list of links to pages.

[Live demo](http://shadowen.github.io/Jekyll-paginator-links)

# Usage
1. In your `_config.yml`, add the line:

	paginate: 5
  Note the number you set here is the number of posts/page.
1. Copy `_includes/paginator-links.css` and `includes/paginator-links.html` to your own `_includes/` folder.
1. In your `index.html` (or wherever you're paginating), paste the following segment:

	<style>{% include paginator-links.css %}</style>
	{% include paginator-links.html maxPages=5 %}

# Inspiration
- http://stackoverflow.com/questions/14025597/liquid-and-arithmetic
- http://stackoverflow.com/questions/27963027/jekyll-long-pagination-how-to-shorten-it
- http://stackoverflow.com/questions/30125878/can-i-have-a-proper-nice-tiled-pagination-in-jekyll-using-liquid-templates