OSEDLabHelpers/
│├── 01_pattern_offset/
│   
├── pattern_offset_pwntools.py   # interactive script using pwntools
│   └── pattern_offset_pure.py       # pure Python version
│├── 02_badchar_test/
│   ├── badchar_test.py               # interactive bad character testing
│├── 03_shellcode_inject/
│   ├── shellcode_inject.py           # interactive shellcode injection
│└── README.md                         # explain each script, usage, and notes


OSED study notes,using Vulnserver as a test case.
- The pattern offset scripts ,can be used to crash the buffer ,then write the pattern to find the exact location of the EIP .
