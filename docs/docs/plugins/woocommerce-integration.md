
# WooCommerce Integration

This Enthusiast plugin enables import of product data directly from WooCommerce

## Installing plugin `enthusiast-source-woocommerce`

### Install using pip

```shell
pip install enthusiast-source-woocommerce
```

### Enable plugin

Edit `server/pecl/settings.py`

```python title="server/pecl/settings.py"
CATALOG_PRODUCT_SOURCE_PLUGINS = {
    ...
    "WooCommerce": "enthusiast_source_woocommerce.WoocommerceProductSource"
}
```

### Authentication (using environment variables, optional)

WooCommerce API credentials directly under your environment variables or in docker compose file

```shell
WOO_CONSUMER_KEY=consumerkey
WOO_CONSUMER_SECRET=consumersecret
```

**You can also set Consumer Key and Secret in [sources configuration](#authentication)**

### Restart server

In order to apply changes made, restart the server.

## 2. Sources configuration

### Base URL

Provide base url to your WooCommerce API instance

```json
{
  "base_url": "BASE_URL",
}
```

### Authentication

Provide your WooCommerce API credentials

```json
{
    ...
  "consumer_key": "consumerkey",
  "consumer_secret": "consumersecret"
}
```

### Additional attributes

`per_page`  

By default synchronization will obtain 20 products per page.  

`Min. 10, max 100`

```json
{
    ...
  "per_page": 10
}
```

## 3. Example configuration for source

```json
{
    "base_url": "http://localhost:8080",
    "consumer_key": "consumerkey",
    "consumer_secret": "consumersecret",
}
```
