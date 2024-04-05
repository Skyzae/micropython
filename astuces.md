
cd mpy-cross
make -j

cd port/unix 
make USER_C_MODULES=../../examples/usercmodule
./build-standard/micropython 

cd ports/rp2/
export PICO_SDK_PATH=/home/adrien/pico/pico-sdk

make -j BOARD=RPI_PICO_W submodules
make -j BOARD=RPI_PICO_W USER_C_MODULES=../../examples/usercmodule/micropython.cmake
cd build-RPI_PICO_W/

