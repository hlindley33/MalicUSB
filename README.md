#MalicUSB
This repository is used for code used to exfiltrate data from the target of the USB attack.
Since this is graduate research no data but the username and computer name may be extracted.
There are a few type of ways to exfiltrate the data that is being explored.  The current payloads use duckyscript to execute HID attacks quickly.
In the future Office Product macro attacks will be explored, but these must be opened on the target computer, unlike an HID attack which is automatically executed.

Currently these attacks are simple because the data being extracted is readily available, but these methods can be used to do much more than I currently have shown.
This is just a simple example without any malicious intent.

1. Road apple
2. Social Engineering
3. Insertion of device into an unoccupied computer
4. Embed malware in a file on the USB and wait for it to be opened

The current issue with HID attacks is they are operating system dependent so the USB with the malware must specifically be targeted at an OS
This is not an issue with embedded malware in a document.

###Ways of exfiltration
1. Windows: TcpClient via Powershell
2. Windows: Email using Net.Mail.Mailmessage and Net.Mail.SMTPClient via Powershell
3. Mac: curl via terminal

For 1. and 3. a simple netcat listening on the designated ports will receive the data you need.
For 2. Make use your email server and a trash account to send the data and receive the data.
Replace any <> with your specific variable.

Added line for a command prompt/terminal to display "This disk has a corrupted sector.  Please contact the manufacturer for further instruction."
This is to lead to less questioning by unknowing users.
