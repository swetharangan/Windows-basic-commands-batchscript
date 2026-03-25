# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript
# Name : SWETHA R
# Register No.: 212223040221
# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
```
mkdir my-folder
```
<img width="1544" height="56" alt="Screenshot 2026-03-13 152132" src="https://github.com/user-attachments/assets/922ab58a-fc5c-4381-82c0-c4cc006bb7f3" />

Remove the directory "my-folder"

## COMMAND AND OUTPUT
```
rmdir my-folder
```
<img width="1509" height="60" alt="Screenshot 2026-03-13 205910" src="https://github.com/user-attachments/assets/125d190b-1bcb-4eed-b27b-4fb4bc085217" />


Create the file Rose.txt

## COMMAND AND OUTPUT
```
type nul > Rose.txt
```
<img width="1576" height="41" alt="Screenshot 2026-03-13 205917" src="https://github.com/user-attachments/assets/9c1dacdc-88cd-4332-9e5c-75f51bf5c738" />


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
```
echo Hello World > hello.txt
```
<img width="1709" height="52" alt="Screenshot 2026-03-13 205926" src="https://github.com/user-attachments/assets/253ec544-35a0-4ef3-9179-f9a9dbb50c03" />


Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
```
copy hello.txt hello1.txt
```
<img width="1798" height="77" alt="Screenshot 2026-03-13 205936" src="https://github.com/user-attachments/assets/afb75737-31cc-4a51-ba87-351cb68b9f32" />

Remove the file hello1.txt

## COMMAND AND OUTPUT
```
del hello1.txt
```
<img width="1822" height="46" alt="Screenshot 2026-03-13 205943" src="https://github.com/user-attachments/assets/81406ffa-51ad-4f64-834f-b9c1dde82ab6" />

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
```
dir hello1.txt
```
<img width="1751" height="176" alt="Screenshot 2026-03-13 205953" src="https://github.com/user-attachments/assets/b9e5f16e-3c4b-4eec-85f5-bb0a4f2f3e9c" />

List out all the associated file extensions 


## COMMAND AND OUTPUT
```
assoc
```
<img width="1918" height="631" alt="Screenshot 2026-03-13 210006" src="https://github.com/user-attachments/assets/06a745e8-2389-42f8-92c1-620f2050e415" />

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
```
fc hello.txt Rose.txt
```
<img width="1918" height="631" alt="Screenshot 2026-03-13 210006" src="https://github.com/user-attachments/assets/f88a982b-18eb-456b-9e6d-882add9c06cc" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
## CODE
```
@echo off
set name=John
echo Hello, %name%
pause
```

## OUTPUT
<img width="1651" height="62" alt="Screenshot 2026-03-13 211340" src="https://github.com/user-attachments/assets/22904b6a-bda7-4abc-ac82-da0be7e203ef" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
## CODE
```
@echo off
:START
set /p num=Enter a number: 

set /a rem=%num% %% 2

if %rem%==1 (
    echo The number %num% is ODD
) else (
    echo The number %num% is NOT ODD
)

:CHOICE
set /p choice=Do you want to check another number? (Y/N): 

if /I "%choice%"=="Y" goto START
if /I "%choice%"=="N" goto END

echo Invalid choice. Please enter Y or N.
goto CHOICE
:END
echo Thank you!
pause
```


## OUTPUT

<img width="1897" height="182" alt="Screenshot 2026-03-13 211352" src="https://github.com/user-attachments/assets/6d3fa04d-21d6-4375-bed3-feb218057f7b" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
## CODE
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```



## OUTPUT

<img width="1874" height="149" alt="Screenshot 2026-03-13 211413" src="https://github.com/user-attachments/assets/02a6f650-b882-4d39-90e0-9a9aa98b99a4" />



Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

## CODE
```
@echo off
if exist sample.txt (
    echo sample.txt exists
) else (
    echo sample.txt does not exist
)
pause
```

## OUTPUT

<img width="1702" height="60" alt="Screenshot 2026-03-13 211422" src="https://github.com/user-attachments/assets/547b819d-a400-4f0e-8211-49858532a62a" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
## CODE
```
@echo off
:MENU
cls
echo ===== MENU =====
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
echo =================
set /p choice=Enter your choice: 

if "%choice%"=="1" goto HELLO
if "%choice%"=="2" goto CREATE
if "%choice%"=="3" goto EXIT

echo Invalid choice!
pause
goto MENU

:HELLO
echo Hello, World!
pause
goto MENU

:CREATE
echo This is a new file > newfile.txt
echo File created successfully!
pause
goto MENU
:EXIT
echo Goodbye!
pause
exit
```


## OUTPUT 1
<img width="1919" height="212" alt="Screenshot 2026-03-13 210903" src="https://github.com/user-attachments/assets/d42ac0ad-8082-4e96-a4ad-632737f98217" />

## OUTPUT 2
<img width="1919" height="231" alt="Screenshot 2026-03-13 210915" src="https://github.com/user-attachments/assets/cf20a1f4-dc4b-4dbb-a1eb-64b567743401" />


## OUTPUT 3
<img width="1919" height="213" alt="Screenshot 2026-03-13 210925" src="https://github.com/user-attachments/assets/ba90f12a-26eb-4cac-8873-19f717750e05" />



# RESULT:
The commands/batch files are executed successfully.

