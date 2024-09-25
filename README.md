change the ‘Sale’ badge to the percentage % sale: -10% for example in stead of the word Sale

Find the Product listing liquid file and search for the badge code then Replace the Badge code with the code below

```html
{%- if product.price < product.compare_at_price -%}
  {%- assign savings = product.compare_at_price | minus: product.price | times: 100.0 | divided_by: product.compare_at_price | round | append: '%' -%}
  <span class="badge price__badge-sale color-{{ settings.sale_badge_color_scheme }}">{{ savings }} OFF</span>
{% else %}
<span class="badge price__badge-sale color-{{ settings.sale_badge_color_scheme }}">
  {{ 'products.product.on_sale' | t }}
</span>
{%- endif -%}
