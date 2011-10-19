# A Sitemap.xml Template

```html
---
layout: nil
---
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"
        xmlns:image="http://www.sitemaps.org/schemas/sitemap-image/1.1"
        xmlns:video="http://www.sitemaps.org/schemas/sitemap-video/1.1">
  {% for post in site.posts %}
  <url> 
    <loc>http://metaskills.net{{ post.url }}</loc> 
    {% if post.lastmod %}
    <lastmod>{{ post.lastmod | date_to_xmlschema }}</lastmod>
    {% else %}
    <lastmod>{{ post.date | date_to_xmlschema }}</lastmod>
    {% endif %}
  </url>
  {% endfor %}
</urlset>

```

# Usage

Put a optional lastmod date in your YAML front matter.

```
--- 
layout: post
title: Authenticated S3 GETs For Private Objects Using Paperclip
lastmod: 2011-10-18
...
---
```
