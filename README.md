# convert.bat
convert.bat is used for Bilkent EEE 212 course while programming the FRDM-KL25Z without uploading the code from Keil uVision 5 IDE. It helps when you cannot use Premicro Debugger to load code to KL25Z. This case presents (commonly in Windows 11) as your PC not supporting/recognizing KL25Z board and you cannot use "Download" operation on uVision. Instead of Premicro Debugger, this code uses fromelf tool downloaded within uVision 5.

## Code
convert.bat has this code loaded:
"C:\Keil_v5\ARM\ARMCLANG\bin\fromelf.exe" --bin .\*.axf --output .\test.srec

## Operation
When you "Build" or "Rebuild" a project in uVision 5 a file with the extention of .axf appears on the objects folder of the project)
Fromelf tool converts any .axf file within the same folder into a .srec file (make sure you have a single file with .axf extention before running convert.bat)
You can copy the test.srec file to FRDM-KL25Z location (memory of the board) (If your PC does not recognize the board as a memory location, you probably have some other driver issues)
The board automatically loads the code after unplugging and plugging back the board to your PC

## How to make/edit convert.bat 
To create the .bat extention file
- Open a .txt file
- Copy/paste the above code
- Save the txt and rename it to convert.bat
- Move the file to the folder where you will have .axf files

### Editing
If you have installed uVision 5 somewhere else instead of C drive of Windows, you can change the file address. To do so, 
- right-click to convert.bat
- click "Edit in Notepad" or any other note writing program
- change the file address (make sure that the file address you write has fromelf.exe)
- save and close the file
  
If you want to convert just a specific named file with .axf extention, write the filename instead of *
If you want to change the output file name, change test 
(Do not change file extentions .axf .srec or .bat)
