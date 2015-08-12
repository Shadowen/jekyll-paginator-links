[Live demo](http://shadowen.github.com/Jekyll-paginator-links)

# Usage
1. In your `_config.yml`, add the line:
		paginate: 5
	Note the number you set here is the number of posts/page.
1. Copy `_includes/paginator-links.css` and `includes/paginator-links.html` to your own `_includes/` folder.
1. In your `index.html` (or wherever you're paginating), paste the following segment:
		<style>{% include paginator-links.css %}</style>
		{% include paginator-links.html maxPages=5 %}
