# schema.contao.org

This repository contains the schema.org vocabulary for Contao. Use the
following Nginx configuration to dispatch it:

```
location / {
  default_type application/ld+json;
  rewrite ^/$ /index.jsonld break;
  rewrite ^(.+)$ $1.jsonld break;
  expires 1d;
  add_header "Access-Control-Allow-Origin" "*";
}
```
