# pymemimporter
pymemimporter is a funny PoC that allows you to import any .pyd from memory with only pure python code (no .pyd) ! 
It basically executes a shellcode with ctypes to add \_memimporter (from py2exe project) as a builtin python module :D

based on Joachim Bauch's MemoryModule (https://github.com/fancycode/MemoryModule) and Didier Stevens' ShellCodeMemoryModule (https://blog.didierstevens.com/programs/shellcode/)

Only implemented for python 32bit on Windows
usage: 
```
C:\Users\me\Desktop>python
Python 2.7.11 (v2.7.11:6d1b6a68f775, Dec  5 2015, 20:32:19) [MSC v.1500 32 bit (Intel)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import pymemimporter
>>> import _memimporter
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  ImportError: No module named _memimporter
>>> pymemimporter.init()
>>> import _memimporter
>>> _memimporter
<module '_memimporter' (built-in)>
>>>
```
## examples
running example/mimikatz32.py will load from memory a mimikatz interactive shell using only .py files as dependencies

