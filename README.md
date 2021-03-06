------------------------------------------------------ JDG Shell Manual ------------------------------------------------------

This is a simple linux shell, written in c, that can be run in either batch mode or
interactive mode. It features file input and output redirection, pipes, background
processing, and parrallel processing. These features are disccused in depth later in this
manual. We will first talk about running the shell in interactive mode.

In interactive mode, the user can run any shell command, built in or external, to get work
done. Any valid linux command, and/or flags, will be processed by the shell and produce
the desired output. Please refer to the linux man pages for info on external commands.
This can be done by using the command "man ls", for example. The shell also includes a
variety of built in commands. Below contains the full list.

        Name:
                cd
        Usage:
                cd <path>
        Description:
                will change the current directory to 'path', if it exists
                does not change current directory if it fails

        Name:
                clear
        Usage:
                clear
        Description:
                will clear all contents of stdout screen

        Name:
                dir
        Usage:
                dir
        Description:
                print everything in the current working directory

        Name:
                echo
        Usage:
                echo 'cmd'
        Description:
                prints 'cmd' to stdout

        Name:
                envp
        Usage:
                envp
        Description:
                print the current shell enviorment strings

        Name:
                exit
        Usage:
                exit
        Description:
                exit the shell program

        Name:
                help
        Usage:
                help 'cmd'
        Description:
                prints usefull info about the 'cmd'

        Name:
                pause
        Usage:
                pause
        Description:
                pause unitl user hits enter key

The commands listed above are all of the valid built in shell commands.
These commands, as well as external commands, can all be handled with this shell.

We will now discuss running the shell with a batch file. A batch file contains
valid shell commands, or invalid, that will be processed by the shell and produce the
desired output. The batchfile must not contain any new lines after the last command.
A batchfile could be as simple as one command, for example "dir". The batch file
should be a plain text file, so for this example lets say the file is named "batch".
To run the shell in batch mode with this batchfile, we would
enter the command "myshell batch". All the desired output will be printed to stdout, or
a file if any redirection is specifieced.

This shell supports file input and output redirection, which we will be disscussing now.
File redirection is a way for processes to either send or get information to/from files
and other places, that are not stdout or stdin. This is a convenient way for the user
to handle their information.

To use input redirection, the command is "<". An example
of this would be the command "wc < my_file". In this command, we are redirecting the
input for the command "wc" from stdin to the file "my_file". Word count, "wc", will count
the number of lines, characters, and bytes, from the supplied input.

For output redirection, the command to use is ">". A simple example of this would be
the command "ls > out.txt". Here, we are redirecting the output of the command "ls" from
stdout to the file "out.txt". Instead of printing to the the terminal screen, the command
will write the output to the file specified.

There is also an append command, which is ">>". This command is similar to the output
redirect, but the file specified must already exist. This command does not create the
file if it does not exist. An exaple of this command is "who >> out.txt". This command
will append the output of "who" to the file "out.txt". In order for this example to work,
and the append command in general, is that file specified must exist.
