## envoy js/ts protobuf api

generate from [https://github.com/envoyproxy/envoy/tree/main/api](https://github.com/envoyproxy/envoy/tree/main/api)

generate commands:

```
cd envoy/api
rm -rf buf.lock
buf dep update

buf generate

buf generate buf.build/prometheus/client-model
buf generate buf.build/opentelemetry/opentelemetry
buf generate buf.build/gogo/protobuf
buf generate buf.build/cncf/xds
buf generate buf.build/envoyproxy/protoc-gen-validate
buf generate buf.build/googleapis/googleapis:62f35d8aed1149c291d606d958a7ce32
```

buf.gen.yaml

```
# buf.gen.yaml
version: v2
plugins:
  - remote: buf.build/bufbuild/es:v2.10.0  # 生成TS代码的官方插件
    out: ./ts_out # 输出目录
```

install package

```
pnpm install git+ssh://git@github.com:smartyhero/envoy-data-plane-api-es.git#v1.36.3
```
