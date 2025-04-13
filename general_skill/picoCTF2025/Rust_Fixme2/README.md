# picoCTF2025 - General Skill - Rust Fixme2

- Write-Up Author: W4yn3Tr4n

- Flag: picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

## Challenge Description:

The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?
Download the Rust code [here](https://github.com/Waynehck8/wu/edit/picoCTF2025/general_skill/picoCTF2025/Rust_Fixme2/fixme2.tar.gz)

## Write up  
Source Code: 
![image](https://github.com/user-attachments/assets/3e9f1959-de60-4ca5-8eb8-443a496dedaf)



Objective of this challenge is checking error syntax and fixing the code then compiling, after checking syntax through the error   

![image](https://github.com/user-attachments/assets/a37a0d2f-8600-4623-9173-6f79ffc87d88)

Two errors: 
1.  mismatched types
2.  cannot borrow `borrowed_string` as mutable, as it is not declared as mutable

After fixing it 

![image](https://github.com/user-attachments/assets/6522ad07-647a-4810-a14d-3d53ade57c15)
Fixing it: 
1. Making the `borrowed_string` declared as mutable
2. Deleting the `&` before the party_foul because we want to passing the variable not a reference

Compile & run and we get the flag

![image](https://github.com/user-attachments/assets/0597eec3-90a2-4fda-a238-796b15cc0332)






