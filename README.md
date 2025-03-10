# async_google_trans_new
[![PyPI - Version](https://img.shields.io/pypi/v/async_google_trans_new?style=flat-square)](https://pypi.org/project/async-google-trans-new) [![PyPI - Downloads](https://img.shields.io/badge/dynamic/json?style=flat-square&label=downloads&query=%24.total_downloads&url=https%3A%2F%2Fapi.pepy.tech%2Fapi%2Fprojects%2Fasync_google_trans_new)](https://pepy.tech/project/async-google-trans-new/)

This is a library based on [google_trans_new](https://github.com/lushan88a/google_trans_new) but it is async!  
It's very easy to use and solve the problem that the old api which use tk value cannot be used.  
This interface is for academic use only, please do not use it for commercial use.  
  
***
  
  
Installation
====
Run this:
```bash
pip install async-google-trans-new
```

***
  
  
Basic Usage
=====
### Translate
```python
import asyncio
import async_google_trans_new  

 
async def coro():
    g = async_google_trans_new.AsyncTranslator()
    print(await g.translate("こんにちは、世界！","en"))

loop = asyncio.get_event_loop() 
loop.run_until_complete(coro())
-> Hello world!
```
***

Advanced Usage
=====
### Translate 
### Multi Translate
```python
import asyncio
from async_google_trans_new import AsyncTranslator

 
async def coro():
    g = AsyncTranslator()
    texts = ["こんにちは、世界！", "こんばんは、世界！", "おはよう、世界！"]
    gathers = []
    for text in texts:
    	  gathers.append(g.translate(text, "en"))
    
    print(await asyncio.gather(*gathers))

loop = asyncio.get_event_loop() 
loop.run_until_complete(coro())
-> ['Hello World! ', 'Good evening, the world! ', 'Good morning, the world! '] 
```
***

Prerequisites
====
* **Python 3.8 (Please make GitHub issue if you can use this lib on different python version)**  
* **aiohttp**  
* **urllib3**  
***
  
License
====
Please see [LICENSE](https://github.com/sevenc-nanashi/async_google_trans_new/blob/main/LICENSE).
