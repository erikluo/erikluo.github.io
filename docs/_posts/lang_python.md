## Python
**帮助文档**<br>
- [python builtin functions](https://docs.python.org/3/library/functions.html#func-list)

**启动http服务器** <br>
```
# python2
python2 -m SimpleHTTPServer 8080

# python3
python3 -m http.server 8080
```

**日志方案**<br>
- logging
```
import logging
logging.basicConfig(stream=sys.stdout, level=logging.DEBUG,
                    format='%(asctime)s - %(levelname)s - %(filename)s:%(funcName)s:%(lineno)s - %(message)s')

```

- loguru
```
from loguru import logger
```

### python Web框架
**web框架文档**<br>
- [django](https://www.djangoproject.com/)
- [django github](https://github.com/django/django)
- [flask github](https://github.com/pallets/flask)
- [aiohttp](https://docs.aiohttp.org/en/stable/)

**web框架应用**<br>
- [aiohttp -> ray dashboard实现](https://github.com/ray-project/ray/)
- [flask -> Web自建图床](https://gitee.com/staugur/picbed)
