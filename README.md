# Tensorflow Serving Client with Python3 

* python3 演示客户端

## 注意
* `channel = implementations.insecure_channel('172.17.0.5', int(8500))`
  > 地址 `172.17.0.5` 为 tensorflow serving 容器地址，，没有做端口映射，要保证客户端容器 `IP` 地址与 tensorflow serving 容器 IP 地址在同一子网内。