# atari_py

[![Build Status](https://travis-ci.org/openai/atari-py.svg?branch=master)](https://travis-ci.org/openai/atari-py)

A packaged and slightly-modified version of [https://github.com/bbitmaster/ale_python_interface](https://github.com/bbitmaster/ale_python_interface).

#### Avoid if you know what is this for
May be you can fix build issues and install missing libraries as and when you find erros, but I would still prefer to have extra build tools already installed to avoid runing into issues later.
  - Download Community Visual Studio from https://www.visualstudio.com/downloads/
  - While installation make sure to check/ download "Desktop development for C++". This will install required libraries like Visual C++ tool for cmake.
  - You might get some Win10SDK installation error, in case you do, first install the SDK from here https://developer.microsoft.com/en-us/windows/downloads/windows-10-sdk and then re-try installating "Desktop development for C++"


#### Installing atari
Similar to what rybskej built here for an older version of atari: https://github.com/rybskej/atari-py
  - Install MSYS2 and follow post-install instructions: https://msys2.github.io/
  - Install MSYS2 packages (via MSYS terminal): <br/>```pacman -S base-devel mingw-w64-x86_64-gcc mingw-w64-x86_64-cmake```
  - Append to current Windows User PATH: ";C:\msys64\mingw64\bin;C:\msys64\usr\bin" <br/> i.e. Start->right-click Computer->Properties->Advanced System Settings->Environment Variables->edit User variables PATH
  - Install Xming: [https://sourceforge.net/projects/xming/])(https://sourceforge.net/projects/xming/)
  - Then add a new windows environment/ user variable (same method as #3): Name=DISPLAY, Value=:0 <br/> Or just remember to set it in your cmd.exe environment before running python:<br/> ```set DISPLAY=:0```
  - Install atari-py and OpenAI Gym:<br/> ```git clone https://github.com/AbhishekAshokDubey/atari-py.git```<br/> ```cd atari-py && make && python setup.py install && pip install "gym[atari]"```
  - If you get some issue while installing gym[atari], dun panic, as long as the make command worked for you, just append the path of 'atri-py' folder to the PYTHONPATH variable in environment variables.


### Next
```import gym
env = gym.make('Pong-v0')
env.reset()
env.render()
env.close()```
