# atari_py

[![Build Status](https://travis-ci.org/openai/atari-py.svg?branch=master)](https://travis-ci.org/openai/atari-py)

A patched version of [atari_py](https://github.com/openai/atari-py) for windows.
<br/>Tested on windows 7.

#### Jump directly to the next section, if you know what is this for
  - Download Community Visual Studio from https://www.visualstudio.com/downloads/
  - While installation make sure to check/ download "Desktop development for C++". This will install required libraries like Visual C++ tool for cmake.
  - You might get some Win10SDK installation error, in case you do, first install the SDK from here https://developer.microsoft.com/en-us/windows/downloads/windows-10-sdk and then re-try installating "Desktop development for C++"


#### Installing atari
Similar to what rybskej built here for an older version of atari: https://github.com/rybskej/atari-py
  - Install MSYS2 and follow post-install instructions: https://msys2.github.io/
  - Install MSYS2 packages (via MSYS terminal): <br/>```pacman -S base-devel mingw-w64-x86_64-gcc mingw-w64-x86_64-cmake```<br/>Make sure it is accesible by appending it to the ```path``` user/ environment variable <br>i.e Append ";C:\msys64\mingw64\bin;C:\msys64\usr\bin" to the ```path``` variable<br/> 
  - Install Xming: https://sourceforge.net/projects/xming/
  - Then add a new windows environment/ user variable: Name=DISPLAY, Value=:0
  - Install atari-py and OpenAI Gym:<br/> ```git clone https://github.com/AbhishekAshokDubey/atari-py.git```<br/> ```cd atari-py && make && python setup.py install && pip install "gym[atari]"```
  - If you get some issues while pip installing ```gym[atari]```, dun panic, as long as the make command worked for you, just append the path of the main 'atri-py' folder on your system to the ```PYTHONPATH``` variable in the environment variables.


### Next
```import gym
env = gym.make('Pong-v0')
env.reset()
env.render()
env.close()
