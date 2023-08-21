## API SPEC
- [OpenAPI规范](https://github.com/OAI/OpenAPI-Specification)
- [Swagger Open Source](https://github.com/swagger-api)
- [go-swagger](https://github.com/go-swagger/go-swagger)
- [apifox](https://apifox.com/)

## Swagger
如何查看?
```
docker run --rm -p 80:8080 swaggerapi/swagger-ui
```
如何可视化编辑?
```
docker run --rm -p 80:8080 swaggerapi/swagger-editor
```

如何生成API SPEC文件？
- 手写yaml
- [从go源码生成](https://github.com/go-swagger/go-swagger#generate-a-spec-from-source)
