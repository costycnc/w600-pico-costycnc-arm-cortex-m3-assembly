<p dir="auto">Inspired from <a href="https://github.com/gmcgarry/w600">https://github.com/gmcgarry/w600</a></p>

<h1 tabindex="-1" dir="auto"><a id="user-content-introduction" class="anchor" aria-hidden="true" href="#introduction"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a>Introduction</h1>

<p dir="auto">I try to compile myself like this upper link but without success.I use w600-pico module like this <a href="https://www.wemos.cc/en/latest/w600/w600_pico.html">https://www.wemos.cc/en/latest/w600/w600_pico.html</a>. After installed w600 board how see in this <a href="https://github.com/costycnc/w600-pico-arduino/tree/main/how%20compile%20w600%20with%20python3%20and%20w600tool">link</a> and working good!!! but not enough ! Until i discover pack for arduino sam board .</p>

<p dir="auto">So i decided to use arduino ide to compile this code write in assembler.So ... I succeeded to obtain elf file from this asm code.From arduino boards manager i installed Arduino SAM boards(32-bits ARM Cortex-M3).</p>



![image](https://github.com/costycnc/w600-pico-costycnc-arm-cortex-m3-assembly/assets/3405110/b3e6dcde-d2b7-4ca1-acdc-7700f0dc8b46)


![image](https://github.com/costycnc/w600-pico-costycnc-arm-cortex-m3-assembly/assets/3405110/fd250395-aff3-46f4-9eb2-f2ee72a401ce)



      platform.txt w600

      recipe.objcopy.hex.pattern="{runtime.tools.wmtool.path}/{compiler.wmtool.cmd}" "{runtime.tools.wmtool.path}" "{compiler.path}{compiler.obj.cmd}" 
                                  "{build.path}/{build.project_name}.elf" "{build.path}/{build.project_name}.bin" "{secboot.img.path}"
      
       
      runtime.tools.wmtool.path={runtime.tools.wmtools.path}
      runtime.tools.wmtool.path=C:\Users\costycnc\AppData\Local\Arduino15\packages\w600\tools\wmtools\0.3.2
      
      compiler.wmtool.cmd=wmtool.bat
      
      compiler.path={runtime.tools.gcc-arm-none-eabi.path}/bin/
      compiler.path=C:\Users\costycnc\AppData\Local\Arduino15\packages\w600\tools\gcc-arm-none-eabi\4_9-2015q1-20150306/bin/
      
      compiler.obj.cmd=arm-none-eabi-objcopy
      
      build.path= temp
      
      build.project_name = name ino file ( example blink.ino )
      
      secboot.img.path={runtime.platform.path}/bootloaders/secboot/secboot.img
      secboot.img.path=C:\Users\costycnc\AppData\Local\Arduino15\packages\w600\hardware\w600\0.2.6/bootloaders/secboot/secboot.img
