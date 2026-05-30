---
layout: home
---

# 欢迎来到 zhou557 的博客

这里记录我的技术学习、思考和分享。

## 最新文章

{% for post in paginator.posts %}
### [{{ post.title }}]({{ post.url }})
{{ post.date | date: "%Y-%m-%d" }}
{{ post.excerpt }}
{% endfor %}

{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">上一页</a>
  {% else %}
    <span>上一页</span>
  {% endif %}
  
  {% for page in (1..paginator.total_pages) %}
    {% if page == paginator.page %}
      <em>{{ page }}</em>
    {% elsif page == 1 %}
      <a href="{{ '/' | prepend: site.baseurl | replace: '//', '/' }}">{{ page }}</a>
    {% else %}
      <a href="{{ site.paginate_path | prepend: site.baseurl | replace: '//', '/' | replace: ':num', page }}">{{ page }}</a>
    {% endif %}
  {% endfor %}
  
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">下一页</a>
  {% else %}
    <span>下一页</span>
  {% endif %}
</div>
{% endif %}
