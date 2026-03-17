---
layout: page
title: About
permalink: /about/
---

Another blog by a nerdy loser on the internet. What more do you need to know?

Here's all the web 1.0 style buttons I currently host. Message me so that I can showcase yours here! :D

<div style="display:grid; grid-auto-flow:row; grid-template-columns: 1fr; padding-top: 1vw;">
{% assign button_img = site.static_files | where_exp: "file", "file.path contains 'buttons/'" %}
{% for img in button_img %}
    {% assign alt_text = site.data.buttons[img.name].alt | default: img.basename %}
    {% assign click_link = site.data.buttons[img.name].link | default: nil %}
    {% assign img_txt = site.data.buttons[img.name].txt | default: alt_text %}

    <div style="display:grid; grid-template-columns: 1fr 1fr; align-items: center; justify-items: center; padding-bottom: 1vw;">
    {% if click_link %}
    <a href = "{{ click_link }}">
        <img src="{{ img.path | relative_url }}" alt="{{ alt_text }}" width="88" height="31" >
    </a>
    {% else %}
        <img src="{{ img.path | relative_url }}" alt="{{ alt_text }}" width="88" height="31">
    {% endif %}
    {{ img_txt }}
    </div>
{% endfor %}
</div>

---

<sub>
This website uses the base Jekyll theme. You can find out more Jekyll at: 
[jekyllrb.com](https://jekyllrb.com/)
</sub>
{: style="text-align: center;"}

<sub>
You can find the source code for Minima at GitHub:
[jekyll][jekyll-organization] /
[minima](https://github.com/jekyll/minima)
</sub>
{: style="text-align: center;"}

<sub>
You can find the source code for Jekyll at GitHub:
[jekyll][jekyll-organization] /
[jekyll](https://github.com/jekyll/jekyll)
</sub>
{: style="text-align: center;"}

[jekyll-organization]: https://github.com/jekyll