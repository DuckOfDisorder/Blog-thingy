---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<head>
<link rel="icon" type="image/svg+xml" href="/favicon.svg" />
</head>
<h2>Blog Posts</h2>
<ul class="post-list">
{% assign blog_pages = site.pages | where_exp: "p", "p.path contains 'blogs/'" | sort: "date" | reverse %}
{% for p in blog_pages %}
	<li>
		{% if p.date %}<span class="post-meta">{{ p.date | date: "%b %-d, %Y" }}</span>{% endif %}
		<h3><a class="post-link" href="{{ p.url | relative_url }}">{{ p.title | default: p.name }}</a></h3>
		{% if p.excerpt %}<p>{{ p.excerpt | strip_html | truncate: 160 }}</p>{% endif %}
	</li>
{% endfor %}
</ul>
