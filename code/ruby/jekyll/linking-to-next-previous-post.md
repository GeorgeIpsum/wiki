# Linking to next/ previous post

Open post layout file and add the following (wherever you want the links to appear):

```markup
<div class="page-navigation">
    {% raw %}
{% if page.previous.url %} <!-- this is the important liquid tag that you need to know -->
        <a class="previous" href="{{ page.previous.url }}">&laquo; {{ page.previous.title }}</a>
    {% endif %}
    {% if page.next.url %}
        <!-- same thing, but use &raquo; for double right chevron -->
    {% endif %}
{% endraw %}
</div>
```
