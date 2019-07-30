libwebsock
===========


WebSocket server demo for C

Also, to compile:

./configure --prefix=$PWD/install

make && make install

Then link your C program against echo: 

  gcc -g -O0 -I../install/include -o echo echo.c -L../install/lib -lwebsock
  gcc -g -O0 -I../install/include -o ssl_echo echo-ssl.c -L../install/lib -lwebsock -lssl

  or static compile
  
  export INSTALL_PATH_EX=/home/zouqing/work/auto/vmp/premake/install    # your path of library
  gcc -g -O0 -I$INSTALL_PATH_EX/include -o ssl_echo echo-ssl.c $INSTALL_PATH_EX/lib/libwebsock.a $INSTALL_PATH_EX/lib/libevent.a $INSTALL_PATH_EX/lib/libevent_pthreads.a $INSTALL_PATH_EX/lib/libevent_openssl.a -lpthread -lcrypto -lssl

run:

# export LD_LIBRARY_PATH=$PWD/install/lib
 ./echo 9002
 or
 ./ssl_echo 9002 privkey.pem cacert.pem

