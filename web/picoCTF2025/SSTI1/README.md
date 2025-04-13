# picoCTF2025 - Web Exploitation - SSTI1

- Write-Up Author: W4yn3Tr4n

- Flag: picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_5c985a9a}

## Challenge Description:

I made a cool website where you can announce whatever you want! Try it out!
Additional details will be available after launching your challenge instance.

## Write up  

Click on the Launch Instance button to access the challenge. Paste the given URL in browser and it will open a page as shown below

![image](https://github.com/user-attachments/assets/5a06539c-b52a-42ab-9225-42271326c5b9)


Type in anything and we can see that the input we put in it completely show on the page

![image](https://github.com/user-attachments/assets/a66e833a-d381-4d83-aaa2-7dbee66a5481)

Using Wappalyzer to detect the engines of the page

![image](https://github.com/user-attachments/assets/53006a2e-1ad5-443c-b348-8aa4a2f12397)

Detected that the page using Flask ( Jinja2 ) and using Python for programming this page

According to the name of this challenge "SSTI1" and the testing that we have tested --> SSTI vulnerabilities

Because it using Jinja2 so we can use this example payload {{ 7*7 }} for checking if the SSTI vul is correctly occuring on this page 100%

![image](https://github.com/user-attachments/assets/35568f0b-a4f8-4315-9f96-7edcf4b7a471)

We can use the payload {{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('ls').read() }} for list out the file 
![image](https://github.com/user-attachments/assets/962d71c4-efbb-4bed-bcd7-8c887b2fc7f4)

Ohh!! We can see the file flag ( exactly the file we want to get), so just adjusting a little bit on the payload then we get the flag 

Payload: {{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat flag').read() }}

![image](https://github.com/user-attachments/assets/ca8c511b-08bf-4170-9328-e8b17f6d21fa)














