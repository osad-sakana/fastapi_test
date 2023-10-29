# FastAPIを学ぶ

[参考文献](https://kinsta.com/jp/blog/fastapi/)

## インストールしたもの

```shell
pip install fastapi
pip install "uvicorn[standard]"
```

## Hello world

```py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def root():
  return {
    "greeting": "Hello world",
  }
```

```shell
uvicorn main:app --reload
```

エラーが出ました。

```text
ERROR:    [Errno 48] Address already in use
```

アドレスが占拠されているので、別アドレスを指定してみます。

```shell
uvicorn main:app --reload --port 8010
```

起動できました。

```text
{"greeting":"Hello world"}
```

API立ち上げられています。

## データベースと紐付ける

