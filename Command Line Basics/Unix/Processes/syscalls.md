# Syscalls

## fork()

Creates a copy of the running process. 

Used to allocate memory for the new process and copys over information about the environment (such as who is running hte process, what the working directory is, and environment variables). 

Creates a parent/child relationship.

## exec()

Loads the program into memory and transfers execution to it.

## exit()

Used to terminate self.

## kill()

Used to terminate an existing process

## wait()

Used to await execution of a child process. 

Stands by for return from child.