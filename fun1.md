# Blog Post for Servers and SSH Keys 
**I am Zheng Guo, and this is the second lab report.**
**In this report, I will introduce and explain the string servers that I creaed. Also, I will show the path of private key and public key in my own computer and ieng6**
# Part 1
Code for the String Server:![image](截屏2023-10-18 上午11.02.45.png)
First Screenshot of `/add-message`: ![image](截屏2023-10-18 上午11.10.21.png)
1. Method that is called: start in the server class is called and handleRequest in the handler class is called.
2. For the start method, the arguments are 1983 and `new Handler()`. For the handleRequest method, the argument is the URL http://localhost:1983/add-message?s=Hello. The field `s` originally has the value of empty string. After the first iteration `s` becomes the conbimation of three strings:"1. "+"Hello"+"\n". The field `count` originally has the integer value of 0. After the first iteration `count` becomes 1.
3. `s` changes from empty to ""1. "+"Hello"+"\n"", and `count` changes from 0 to 1.
Second Screenshot of `/add-message`: ![image](截屏2023-10-18 上午11.11.35.png)
1. Method that is called: start in the server class is called and handleRequest in the handler class is called.
2. For the start method, the arguments are 1983 and `new Handler()`. For the handleRequest method, the argument is the URL http://localhost:1983/add-message?s=How are you. The field `s` originally has the value of ""1. "+"Hello"+"\n"". After the second iteration `s` becomes the ""1. "+"Hello"+"\n+"2. "+"How are you"+"\n"". The field `count` originally has the integer value of 1. After the first iteration `count` becomes 2.
3. `s` changes from ""1. "+"Hello"+"\n"" to ""1. "+"Hello"+"\n+"2. "+"How are you"+"\n"", and `count` changes from 1 to 2.
---
# Part 2
