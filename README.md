## 环境搭建
### 下载镜像[leungwensen/cbc-ubuntu-64bit](https://hub.docker.com/r/leungwensen/cbc-ubuntu-64bit)

```shell
docker pull leungwensen/cbc-ubuntu-64bit
```

### 执行镜像

```shell
docker run -t -i leungwensen/cbc-ubuntu-64bit
```

### 执行cbc

> 镜像里的cbc命令为`cbc -Wa,--32 -Wl,-melf_i386`的别名，可以直接执行。

```shell
cbc cbc-ubuntu-64bit/test/hello.cb
# should print "Hello, world!"
./hello
```

## 解析器生成器

```shell
mkdir tmp
cp Adder.jj tmp
cd tmp
javacc Adder.jj
javac Adder.java
# test
java Adder '1+2'
java Adder '1 + 16'
```