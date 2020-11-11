---
title: Application data
layout: dev
---
## afterlife rules
<pre>
{%- for level0 in site.data.afterlife-rules %}
  {%- if level0.size == 2 %}
    {%- assign country_name = level0[0] %}
    {%- assign country = site.data.afterlife-rules[country_name] -%}
    {{ forloop.index }}. {{country_name}}
    {%- for level1 in country %}
      {%- assign state_name = level1[0] %}
      {%- assign state = country[state_name] %}
      {{ forloop.index }}. {{state_name}}
      {%- if state.size == 2 %}
        {%- for level2 in state %}
          {{forloop.index}}. {{level2[0]}}
            {{level2[1]}}
        {%- endfor %}
      {%- else %}
        {{level1[1]}}
      {%- endif %}
    {%- endfor %}
  {% else %}{
    {{forloop.index}}. {{level0[0]}}
    {{level0[1]}} }     
  {% endif -%}
{% endfor -%}
</pre>

## schemas
<pre>
{%- for level0 in site.data.schemas %}
  {%- if level0[1].size == 2 %}
    {%- assign country_name = level0[0] %}
    {%- assign country = site.data.schemas[country_name] -%}
    {{ forloop.index }}. {{country_name}}
    {%- for level1 in country %}
      {%- assign state_name = level1[0] %}
      {%- assign state = country[state_name] %}
      {{ forloop.index }}. {{state_name}}
      {%- if state.size == 2 %}
        {%- for level2 in state %}
          {{forloop.index}}. {{level2[0]}}
            {{level2[1]}}
        {%- endfor %}
      {%- else %}
        {{level1[1]}}
      {%- endif %}
    {%- endfor %}
  {% else %}
  {{forloop.index}}. {{level0[0]}}
    {{level0[1]}}
  {% endif -%}
{% endfor -%}
</pre>

## Collections
<p>{{site.collections.size}} collections</p>
<pre>

{%- for a in site.collections %}
  {{a}}
{% endfor -%}
</pre>
