# picoCTF2025 - Web Exploitation - WebSockFish

- Write-Up Author: W4yn3Tr4n

- Flag: picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_0d3d41e1}

## Challenge Description:

Can you win in a convincing manner against this chess bot? He won't go easy on you!
You can find the challenge [here](http://verbal-sleep.picoctf.net:64555)

## Write up  

We using burpsuit to examine first ( because the challenge name include socket )

![image](https://github.com/user-attachments/assets/24abeb16-076c-47ed-a383-3f3d28c2d9a5)

We can see that it using the socket + eval,mate  function for adjusting the move of each chess 

![image](https://github.com/user-attachments/assets/1d07f076-6efa-4eb1-ad7f-827621dc612e)

Try to change it with a big positive number and small positive number as well 

![image](https://github.com/user-attachments/assets/6136ebac-52f5-4e2b-b342-44d7dd31162d)

Nothing gonna happen with mate function, but eval function is completely different 

![image](https://github.com/user-attachments/assets/d4440dd4-f30b-48a9-aad7-d05b77dadb65)


And we can catch the flag 




