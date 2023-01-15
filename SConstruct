import os
import pdb

TARGET = "firmware"
DEVICE = 'atmega8'


CXX_PATH = r"c:\Users\GPN\AppData\Local\Programs\avr8-gnu-toolchain-3.7.0.1796-win32.any.x86_64\avr8-gnu-toolchain-win32_x86_64\bin"

env = Environment(tools=["mingw"])
env.Replace(CXX="avr-g++")
env.Replace(CXXFLAGS="-Wall -g -Os -mmcu="+ DEVICE)
env.Replace(CPPDEFPREFIX="")
env.Replace(PROGSUFFIX="")
env["SIZE"] = "avr-size"
env["OBJCOPY"] = "avr-objcopy"


env["ENV"]["PATH"]=CXX_PATH
#for each in sorted({*env.keys()}):
#    print(each, " = ", env[each])
#pdb.set_trace()

env.Program(TARGET+".elf", 'acc_lighter.cpp')

# Create hex binary file.
env.Command(TARGET + '.hex', TARGET + '.elf', env['OBJCOPY'] + ' -O ihex $SOURCE $TARGET')

# Compute memory usage.
env.Command(None, TARGET + '.elf', env['SIZE'] + ' -C --mcu=' + DEVICE + ' $SOURCE')
