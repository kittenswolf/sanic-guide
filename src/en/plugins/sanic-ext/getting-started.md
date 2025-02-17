# Getting Started

Sanic Extensions is an *officially supported* plugin developed, and maintained by the SCO. The primary goal of this project is to add additional features to help Web API and Web application development easier.

## Features

- Auto create `HEAD`, `OPTIONS`, and `TRACE` endpoints
- CORS protection
- Predefined, endpoint-specific response serializers
- Argument injection into route handlers
- OpenAPI documentation with Redoc and/or Swagger
- Request query arguments and body input validation

## Minimum requirements

- **Python**: 3.8+
- **Sanic**: 21.9+

## Install

The best method is to just install Sanic Extensions along with Sanic itself:

```bash
pip install sanic[ext]
```

You can of course also just install it by itself.

```bash
pip install sanic-ext
```

## Extend your application

Out of the box, Sanic Extensions will enable a bunch of features for you. 

::: new NEW in v21.12
---:1
To setup Sanic Extensions (v21.12+), you need to do: **nothing**. If it is installed in the environment, it is setup and ready to go.

This code is the Hello, world app in the [Sanic Getting Started page](../../guide/getting-started.md) _without any changes_.
:--:1
```python
from sanic import Sanic
from sanic.response import text

app = Sanic("MyHelloWorldApp")

@app.get("/")
async def hello_world(request):
    return text("Hello, world.")
```
:---
:::

---:1
**_OLD DEPRECATED SETUP_**

In v21.9, the easiest way to get started is to instantiate it with `Extend`.

If you look back at the Hello, world app in the [Sanic Getting Started page](../../guide/getting-started.md), you will see the only additions here are the two highlighted lines.
:--:1

```python{3,6}
from sanic import Sanic
from sanic.response import text
from sanic_ext import Extend

app = Sanic("MyHelloWorldApp")
Extend(app)

@app.get("/")
async def hello_world(request):
    return text("Hello, world.")
```
:---

Regardless of how it is setup, you should now be able to view the OpenAPI documentation and see some of the functionality in action: [http://localhost:8000/docs](http://localhost:8000/docs).
