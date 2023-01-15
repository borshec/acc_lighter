import os
import pdb

CXX_PATH = r"c:\Users\GPN\AppData\Local\Programs\avr8-gnu-toolchain-3.7.0.1796-win32.any.x86_64\avr8-gnu-toolchain-win32_x86_64\bin"

env = Environment(tools=["mingw"])
env.Replace(CXX='avr-g++')
env.Replace(CXXFLAGS='-mmcu=avr4')
env.Replace(CPPDEFPREFIX="")

env["ENV"]["PATH"]=CXX_PATH
#for each in sorted({*env.keys()}):
#    print(each, " = ", env[each])
#pdb.set_trace()
env.Program('firmware', 'acc_lighter.cpp')
print(env["ENV"]["PATH"])
