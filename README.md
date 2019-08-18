# uv_wrapper
下载libuv:wget http://dist.libuv.org/dist/v1.9.1/libuv-v1.9.1.tar.gz
解压libuv:
tar -zxvf libuv-v1.9.1.tar.gz
执行安装执行
sh autogen.sh
cd libuv-v1.9.1
./configure
make
make check
make install
lib 路径：libuv-v1.9.1/.libs/libuv.a
