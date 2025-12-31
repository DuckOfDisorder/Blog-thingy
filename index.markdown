---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<h2> Support Me <a href="https://support.ofdisorder.de"> Here! </a> </h2> <br>
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
	{% if blog_pages == empty %}
	<li>No posts found in the blogs folder yet.</li>
	{% endif %}
</ul>
