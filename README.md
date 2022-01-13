## 借助WebAssmebly编译dcraw渲染raw格式的照片

#### 说明
1. `dcraw.c`文件`fork`自[https://github.com/ncruces/dcraw](https://github.com/ncruces/dcraw)

#### 环境安装
```shell
git clone https://github.com/juj/emsdk.git
cd emsdk
./emsdk install
./emsdk activate
source ./emsdk_env.sh
```

#### 编译
```shell
emcc dcraw.c -lm -DNODEPS -s WASM=1 -s INVOKE_RUN=0 -s EXTRA_EXPORTED_RUNTIME_METHODS='["callMain"]' -o dcraw.js
```