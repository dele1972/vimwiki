java -jar 
 EspStackTraceDecoder.jar
 /home/XXXX/.arduino15/packages/esp8266/tools/xtensa-lx106-elf-gcc/1.20.0-26-gb404fb9-2/bin/xtensa-lx106-elf-addr2line
 /home/XXXX/project/Release/project.elf
 /tmp/dump.txt





java -jar EspStackTraceDecoder.jar ~/snap/arduino/current/.arduino15/packages/esp8266/tools/xtensa-lx106-elf-gcc/2.5.0-4-b40a506/bin/xtensa-lx106-elf-addr2line ./project.elf ./trace.txt


home/lederich/snap/arduino/current/.arduino15/packages/esp8266/tools/xtensa-lx106-elf-gcc/2.5.0-4-b40a506/bin/


https://github.com/littleyoda/EspStackTraceDecoder
https://github.com/me-no-dev/EspExceptionDecoder

## DAS IST DIE LÖSUNG:

you do not need to find it. If you have build the sketch, the plugin will find it for you. If the plugin does not find it, then it's on some custom place that neither me, nor the plugin can tell where it is :)
@pherris
pherris commented on 7 Jan 2017 •

@fabltd the file prompt should only be shown if you have not compiled & uploaded your sketch to your device while the IDE is running. In that case, the tool cannot find the .elf file, therefore it cannot handle the stack trace. To solve this:

    close/open the Arduino IDE (if you've given the tool a .elf location, this seem to be the only way to clear it)
    upload the sketch to your ESP8266
    open the serial monitor and capture your stack trace:

>>>stack>>>
...just the stuff in here
<<<stack<<<

    open the Decoder from the tools menu (you should not be prompted for the file)
    paste the stack trace FTW!

@me-no-dev please correct any nuances that are wrong here. If you'd like I can submit a PR to the README.

https://github.com/me-no-dev/EspExceptionDecoder/issues/19#issuecomment-271082088
