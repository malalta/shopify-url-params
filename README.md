<div align="center">
<img src="https://cdn.shopify.com/shopifycloud/brochure/assets/brand-assets/shopify-logo-primary-logo-456baa801ee66a0a435671082365958316831c9960c480451dd0330bcdae304f.svg"
     alt="Shopify logo"
     width="350" />

# Undocumented Shopify URL Parameters

----

This is a list of useful, mostly undocumented, URL parameters used by Shopify.

**Spot something missing?**  
PRs welcome, or simply let us know in the issues ✌️

----
</div>

## Themes

### Preview an alternative template: `?view=`

```
my-site.com/pages/about-us?view=my-template
                          ^^^^^^^^^^^^^^^^^
```

* This will load `/pages/about-us/` using the liquid template found at
  `templates/page.my-template.liquid`.
* Works for pages, products, collections, and blog posts.

### Test form submission: `?customer_posted=true`

```
my-site.com/any-url/?customer_posted=true
                    ^^^^^^^^^^^^^^^^^^^^^
```

* Useful for testing submission notifications without actually submitting
  the form.
* For example, to see what your customers see when they sign up for your
  newsletter on your homepage, simply view:  
  `my-site.com/?customer_posted=true#contact_form`

## App development

### Get the shopOrigin without cookies: `?shop=`

```
api.your-app.com/?hmac=[...]&shop=client-store.myshopify.com
                             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
```

* When migrating your app away from using third party cookies, it can be
  non-obvious where to get the shopOrigin from after the OAuth handshake.
* The shop name can be read from the `?shop=` query parameter.

## Store admin

### See number of products: `/count.json`

```
my-site.myshopify.com/admin/products/count.json
                                     ^^^^^^^^^^
```

* Unfortunately the Shopify admin doesn't display the number of products 
  in your store. To view this, go to _Products > All Products_ and add
  `/count.json` before the "?" in the URL. 