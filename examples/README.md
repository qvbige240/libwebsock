libwebsock
===========


WebSocket server demo for C

Also, to compile:

./configuer --prefix=$PWD/install

make && make install

Then link your C program against echo: 

  gcc -g -O0 -I../install/include -o echo echo.c -L../install/lib -lwebsock
  gcc -g -O0 -I../install/include -o ssl_echo echo_ssl.c -L../install/lib -lwebsock -lssl

run:

# export LD_LIBRARY_PATH=$(ROOT)/install/lib
 ./echo 9002

