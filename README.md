**OSEDLabHelpers**


OSED study notes,using Vulnserver as a test case.
A series of scripts; 

1.Interactive Crash EIP Offset
- Generates a cyclic pattern of any length.
- Sends the pattern to a vulnerable service.
- Prompts you for EIP after crash.

**Calculates the exact offset to EIP.**
 <img width="559" height="132" alt="image" src="https://github.com/user-attachments/assets/89991dd7-cd29-4d23-b178-36070f7b336d" />


2.Test_EIP_Overwrite

3.Adding bad Chars

4.Generating Shellcode with MSFvenom

 - msfvenom -p windows/exec CMD=calc.exe -b "\x00" -f python EXITFUNC=thread
 - Copy the code into the shellcode portion of the final script
   
5.Final Script
