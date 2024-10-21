# This is my Blog

My name is Ashley, and this is my blog!

I am a senior in high school and I attend the Brooklyn STEAM Center. I am in Full Stack Development and I am  learning Backend Development. I like to read books and watch movies. 

[Here is the link to my personal website](https://adalei1801.github.io/)

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
