# This is my Blog

My name is Ashley, and this is my blog!

I am a First Year at Brandeis University. I am working towards a Computer Science degree. I like to read books and watch movies. 

[Here is the link to my personal website](https://adalei1801.github.io/)

**Blog Posts:**
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
