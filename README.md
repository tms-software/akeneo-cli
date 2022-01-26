Akeneo CLI
==========

You'll need to get an app credentials for Akeneo as explain [here](https://api.akeneo.com/documentation/authentication.html#client-idsecret-generation)

This package use generic calls to Akeneo api. To know the list of available endpoints and how the API work please refer to the official [documentation](https://api.akeneo.com/api-reference-index.html)

CLI
---

The CLI itself is a work in progress. Currently only the product can be retrieved with a command like.

```python
akeneo get product
```


Code
----

```python
import akeneo_cli

akeneo_client = AkeneoClient(
    os.getenv(AKENEO_URL),
    os.getenv(AKENEO_CLIENT_ID),
    os.getenv(AKENEO_CLIENT_SECRET),
)

with akeneo_client.login(os.getenv(AKENEO_USERNAME), os.getenv(AKENEO_PASSWORD)) as session:
  product_list = session.get("products")

  product = session.get("products", code="my-product")

  product-model = session.get("product-models", code="some-model")

  session.patch()

  session.post()

  session.bulk

  session.put_file()
```
