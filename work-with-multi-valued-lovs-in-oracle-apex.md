---
title: Work with multi-valued LOVs in Oracle APEX
layout: default.liquid
---
## Blog!

```
SELECT LEVEL AS element_no,
       regexp_substr(str, '[^:]+', 1, LEVEL) AS value,
  FROM ( SELECT rownum AS id,
                '1:4'     str
            FROM dual
       )
 CONNECT BY instr(str, ':', 1, LEVEL - 1) > 0
     AND id = PRIOR id
     AND PRIOR dbms_random.value IS NOT NULL
```

{% for post in collections.posts.pages %}
#### {{post.title}}

[{{ post.title }}]({{ post.permalink }})
{% endfor %}
