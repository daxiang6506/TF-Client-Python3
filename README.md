# Tensorflow Serving Client with Python3 

python3 演示客户端

## 注意
* `channel = implementations.insecure_channel('172.17.0.5', int(8500))`

  `channel = implementations.insecure_channel('model-server', int(8500))`
  > 地址 `172.17.0.5` 为 tensorflow serving 容器地址，，没有做端口映射，要保证客户端容器 `IP` 地址与 tensorflow serving 容器 IP 地址在同一子网内。   
  > 或者使用容器通过 `--link` 指定的别名
## Run
* 启动 `tensorflow serving` 服务端
  ```
  docker run -it --name model-server -v $(pwd):/bitnami/model-data daxiang6506/tensorflow-serving:1.8.0
  ```

* 下载代码，[github](https://github.com/daxiang6506/TF-Client-Python3)

* 启动 `tensorflow serving` python客户端
  ```
  docker run -p 8883:8888 -d --link model-server -v $(pwd):/notebooks daxiang6506/tensorflow:1.8.0-py3
  ```