## 1.1 Introduction
In this lab, you will interact with the shell and understand how basic commands are executed. You will also learn how to seek help on various commands and topics.

Most Linux commands follow a simple pattern of syntax

command [options…] [arguments…]

We will begin with simple commands and then go on to executing commands with options and arguments.

## 1.2 Step 1
You will begin by running three commands: pwd, ls and uname. These commands, in their simplest forms, are executed without any options or arguments.

At the shell prompt, type the pwd command and press the Enter key. The pwd command displays the directory where the user is currently located in the file system:

```
The working directory is the directory that your terminal window or shell is currently "in". This is also called the current directory. This is an important consideration when you are running commands, since they may behave differently based on the directory you are currently in.
The output of the pwd command (/home/sysadmin in this example) is called a path. The first slash represents the root directory, the top level of the directory structure; home is a directory under the root directory and sysadmin is a directory under the home directory.
```

## 1.3 Step 2
Execute the ls command at the prompt and press Enter; this command will list the files and directories that are in the current directory:

## 1.4 Step 3
The uname command displays information about the current system. Execute the following uname command and review the output:

## 1.5 Step 4
Warning: Linux commands are case sensitive. Running the ls command is not the same as LS or Ls.
Try executing LS at the prompt and notice that it will report an error:

## 1.6 Step 5
Options for Linux commands can be of two types:

Short options are specified with a hyphen (-) followed by a single character.
Long options for commands are preceded by a double hyphen (--) and the option is typically a "full name".
The ls command can be executed using various options. Execute the following ls command with the –a option. You will notice that with the –a option specified, the result now includes entries starting with a . (dot):

ls -a

```
Filenames displayed in different colors denote different file types. For example, blue denotes directories and white denotes plain files.
```

## 1.7 Step 6
The same effect can be achieved by using a long option --all. Execute the following:

ls --all

Warning: If you don't include two hyphens and instead use the option -all, your output will be different because you will really be executing the ls -a -l command.

## 1.8 Step 7
Execute the ls command with the –l option; this will show the listing in long format:

ls -l

## 1.9 Step 8
The –r option for the ls command produces the listing in reverse sorting order. Compare it with the output from ls command executed earlier.

ls -r

## 1.10 Step 9
It is normally possible to combine more than one option in any order. Execute the following ls command with all three options you have previously used:

ls -alr

This ls command output has the combined effect of all the options specified:

-a option includes files starting with a (.)
-l option provides the long listing format
-r option sorts the result in reverse order

Warning: Not all options can be combined. Some options are conflicting; for example, an option to the ls command that sorts files by name would conflict with an option that sorts files by size. Later in this lab you will see how to consult documentation to determine which options will conflict.

## 1.11 Step 10
Just to confirm that it has the same combined effect, specify all of the options separately. You will note that it produces the same result:

ls –a –l -r

## 1.12 Step 11
Earlier, without any options specified, the uname command had produced the output "Linux". Now, execute the uname command with various options and notice the additional information it can display:

uname –a
uname –s
uname –n
uname –m
uname –p
uname –i
uname -o

```
Note that the uname command is providing various system information, including system name (-n) and processor type (-p).
```

## 1.13 Step 12
After the command and its options, many commands will accept one or more arguments. Commands that use arguments may require multiple values. The –w option, when specified with the ls command, can be used to specify the width of the screen (normally this is determined by the actual terminal window size):

ls –rw 40

## 1.14 Step 13
Since the –w option requires an argument, it must be specified at the end of the options. Combining options where the –w option is not at the end will not work. Execute the following command and notice the error that is reported:

ls –wr 40

## 1.15 Step 14
It is not possible to combine multiple options that require arguments. In such a case, they have to appear separately. Execute the following to see a demonstration:

ls –w 40 –I "T*"

```
The option -I will cause the ls command to "ignore" or not display specific files that match a pattern. The pattern "T*" means "any file or directory that begins with a capital T". In this case, the Templates directory was not displayed.
```
