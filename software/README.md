# PicArd Software

PicArd software is composed by:

1. Arduino software
1.1 DC/DC software controller and
1.2 PIC interface

2. PC software
2.1 Executable file
2.2 PIC devices database

# PC software usage

PicArd PC software is a console application for Windows. 

The sintaxe for this application is:

'''
PicArd -c <serial port> -d <device name> [-r read options] [-w write options] [-h <hex file>] [-o <output file>]
'''

where:
    + serial port - [Mandatory]   USB connected to Arduino Uno with PicArd firmware;
    + device name - [Mandadory]   Device name. Example: PIC12F675;
    + -r          - [Optional]    Reads device parameters (use picard -r 0 to see read options);
    + -w          - [Optional]    Writes device parameters (use picard -w 0 to see write options);
    + -h          - [Optional]    Used with -w program and -w all. Specifies hex file to be send to device;
    + -o          - [Optional]    Output file for read options. If omitted, output to screen.
 
 
