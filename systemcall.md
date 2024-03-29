# Systemcalls Benjamin Besic 3AHIF
***
## Posix Calls
### fork
It dublicates a current process and makes a new one, the new process is then called the child process. It has slight differences.

**FAIL: There is insufficient swap space for the new process.**

### stat
Displays a file or file system status with different arguments:
* -L, --derefrence -> follow links
* -f, --file-system -> display file system status instead of file status
* -c, --format=FORMAT ->  use the specified FORMAT instead of the default
* -t, --terse -> print the info in terse form
* --version -> displays version info and exit

### kill
It sends any signal to any process group or process with different arguments:
* -s < signal > -> Specify the signal using name or number
* -l, --list -> list signal names
* -L, --table -> list signal names in a table
* < pid > ... -> send signal to every < pid > listed

**FAIL: The process was suspended**

### mmap
It creates a new mapping in the virtual adress space of the calling process.
With different arguments:
* PROT_... -> describes desired memory protection
* MAP_... -> determines if updates to the mapping are visible to  other processes mapping the same region

### chmod
It changes the file mode of files according to MODE.
With different arguments:
* -f, --silent -> suppress most error messages
* -R, --recursive -> change files and directories recursively
* -v, --verbose -> output a diagnostic for every file processed
* MODE ... -> mode of your choice to change the files

**FAIL: You don't have permission to change the file**

### waitpid
It is working with the fork command. It is used to wait for state changes in a child of the calling  process, and obtain information about the child whose state has changed.
With different arguments:
* pid -> the pid to be waited
* status -> status number
* WUNTRACED -> also return if a child has stopped
* WCONTINUED -> also return if a stopped child has been resumed by delivery of SIGCONT.
***
## Fails
### exec
If the PF_NPROC_EXCEEDED flag is set and the resource limit is still exceeded.

### mount
If you mount a tmpfs with an mpol option.

### read
If fd is not a valid file descriptor or is not open for reading.

### unlink
If another program uses the file.
***
## What is a trap instruction?
A trap instruction is a procedure call that synchronously transfers the control. It is a software interrupt generated by the user program or by an error when the operating system is needed by it to perform the system calls or an operation.
