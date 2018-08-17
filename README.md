# MalicUSB
This repository is used for code used to exfiltrate data from the target of the USB attack.
Since this is graduate research no data but the username and computer name may be extracted.
There are a few type of ways to exfiltrate the data that is being explored.  The current payloads use duckyscript to execute HID attacks quickly.
In the future Office Product macro attacks will be explored, but these must be opened on the target computer, unlike an HID attack which is automatically executed.

Currently these attacks are simple because the data being extracted is readily available, but these methods can be used to do much more than I currently have shown.
This is just a simple example without any malicious intent.

### Ways to get USB into target computer
1. Road apple
2. Social Engineering
3. Insertion of device into an unoccupied computer
4. Embed malware in a file on the USB and wait for it to be opened (Word VBA)

The current issue with HID attacks is they are operating system dependent so the USB with the malware must specifically be targeted at an OS
This is not an issue with embedded malware in a document.  

### Ways of exfiltration
1. Windows: TcpClient via Powershell
2. Windows: Email using Net.Mail.Mailmessage and Net.Mail.SMTPClient via Powershell
3. Mac: curl via terminal
4. Both(Mac is a WIP): Word document with a malicious macro embedded.  The document must be designed in a way that gets the user to click the button on the page to launch the macro. I am not using 'on workbook open' macros because anti-viruses tend to flag them.  If you design where a button will be clicked, then it is much more likely to pass anti-virus detection.  In a real attack code obfuscation would be used as well.  This can also be used to send emails by using code from 2.  Also the form unauthorized needs to be created.  This is a form that needs to appear to like a warning dialog, so the code can run in the background while the user reads the message.  This way even if the confirm button is clicked, a message will show to keep the suspicion down.  

For 1,3, and 4: a simple netcat listening on the designated ports will receive the data you need.
For 2. Use your email server and a trash account to send the data and receive the data.
**Replace any <> with your specific variable.**

For 1-3: Added line for a command prompt/terminal to display "This disk has a corrupted sector.  Please contact the manufacturer for further instruction."
This is to lead to less questioning by unknowing users.
