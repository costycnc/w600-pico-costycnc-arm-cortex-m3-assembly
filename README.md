# w600-pico-costycnc-arm-cortex-m3-assembly

install tool https://developer.arm.com/-/media/Files/downloads/gnu/12.2.mpacbti-rel1/binrel/arm-gnu-toolchain-12.2.mpacbti-rel1-mingw-w64-i686-arm-none-eabi.exe

Set environment variable path with bin path


https://www.mikrocontroller.net/articles/ARM-ASM-Tutorial#Why_assembly?

X  https://armasm.com/docs/getting-to-hello-world/basics/

X  https://github.com/gpit2286/armasm-by-example/tree/master/02-hello-world

X  asm usage https://www.ecb.torontomu.ca/~courses/coe718/lectures/ARM7-M3-Programming.pdf

      source https://community.silabs.com/s/article/disassembling-cortex-m-binary-bin-file-into-assembly?language=en_US
      
      C:\SiliconLabs\SimplicityStudio\v4\developer\toolchains\gnu_arm\4.9_2015q3\bin\arm-none-eabi-objdump.exe
      The tool can also be obtained by downloading the latest version of the GNU ARM Embedded Toolchain maintained by GCC and ARM developers.
      In order to convert a .bin file to assembly .s file, run the following command:
      arm-none-eabi-objdump -D -bbinary -marm <input.bin> -Mforce-thumb > <output.s>
      where <input.bin> is the full path to the input binary file
      and <output.s> is the full path to a file that will contain the assembly file generated by the t

another mode to compile source https://gist.github.com/BobBurns/bb601d3432650073a8b4

      @       lets try to blink an LED on the discovery stm32 L1 board
      @       uses LED on PB7 
      @ how to compile and flash:
      @  arm-none-eabi-as -mcpu=cortex-m3 blinky.s -o blinky.o
      @  arm-none-eabi-ld -v -T stm32.ld -nostartfiles -o blinky.elf blinky.o 
      @  arm-none-eabi-objcopy -O binary blinky.elf blinky.bin
      @ then from st-link (https://github.com/texane/stlink)
      @  ./st-flash write ../first_arm/blinky.bin 0x08000000
