# ALX SE - Simple Shell(hsh)
The simple shell project for [ALX Africa SE](https://www.alxafrica.com/) as part of the C programming phase of the Software Engineering path.

### Prerequisites
Only use the following functions and system calls:
```
access (man 2 access)
chdir (man 2 chdir)
close (man 2 close)
closedir (man 3 closedir)
execve (man 2 execve)
exit (man 3 exit)
fork (man 2 fork)
free (man 3 free)
fstat (man 2 fstat)
getcwd (man 3 getcwd)
getline (man 3 getline)
kill (man 2 kill)
lstat (man 2 lstat)
malloc (man 3 malloc)
open (man 2 open)
opendir (man 3 opendir)
perror (man 3 perror)
read (man 2 read)
readdir (man 3 readdir)
signal (man 2 signal)
stat (man 2 stat)
strtok (man 3 strtok)
wait (man 2 wait)
waitpid (man 2 waitpid)
wait3 (man 2 wait3)
wait4 (man 2 wait4)
write (man 2 write)
_exit (man 2 _exit)
```

### Installing
Compile like this:
```
gcc -Wall -Wextra -Werror -pedantic -g *.c -o hsh
```

## Description of File Structure
1. [builtins.c](builtins.c): 
  * ``is_builtin()`` - checks to see if the command is a builtin, then returns a function pointer to one of the following functions:
  * ``_exit_with_grace`` - exits the shell and frees any malloc'd space.
  * ``_env()`` - prints the current environment.
  * ``_cd()`` - change pwd. Usable with no arguments. ``cd -`` to get to last directory. ``cd ~`` back to home. 
2. [builtins_2.c](builtins_2.c): 
  * ``_setenv_usr()`` - User creates or modifies an environment variable.
3. [env_operations.c](env_operations.c):
  * ``_getenv()`` - recreation of ``getenv()`` from ``<stdlib.h>``. Gets key's value. Returns NULL if not found.
4. [environment.c](environment.c) - Environment and linked lists:
  * ``list_from_path`` - creates linked list from the PATH variable
  * ``search_os()`` - Search the absolute path, current directory, or in PATH``
5. [executor.c](executor.c):
  * ``executor()`` - Executes a command
6. [linked_list_operations.c](linked_list_operations.c):
  * ``add_node()`` - Adds node to linked list of struct type ``env_t``
  * ``free_list()`` - Frees a linked list
  * ``print_list()`` - Prints a linked list
7. [main.c](main.c)
8. [memory_management.c](memory_management.c):
  * ``_realloc`` - Recreates ``realloc`` from ``<stdlib.h>``.
  * ``_memset`` - Fills a memory location with a value for n bytes. 
  * ``_memcpy`` - Copies characters from one place in memory to another.
9. [parser.c](parser.c):
  * ``_getline()`` - Recreation of ``getline()`` from ``<stdio.h>``. Gets a line from stdin, delimited by a ``\n`` character. Also handles ``EOF``. Returns the line, or NULL on error. 
  * ``parser()`` - Parses a string into tokens. Returns a double pointer.
  * global variable ``flag`` for ``signalhandler()`` - Triggers when ``^C`` is hit, then turns off.
  * `sighandler`` - Interrupts the running process if it is not a builtin then prints the prompt again.
  * ``reader()`` - Reads user input, turns it into a string and parses it into tokens. Then it performs actions based on the first token.
10. [shell.h](shell.h) - Header file.
11. [string_operations.c](string_operations.c):
  * ``_strlen()`` - Returns the length of a string. Recreation of ``strlen()`` from ``<string.h>``
  * ``_strncmp()`` - Compares two strings for n bytes, and returns the value of the first difference found. Returns 0 when the last value is the same. Recreation of ``strncmp()`` from ``<string.h>``
  * ``_strdup()`` - Duplicates a string. Recreation of ``strdup()`` from ``<string.h>``
  * ``_strcat_realloc()`` - Concatenates two strings and reallocs a space if either one of the strings are too big to fit in the destination.
  * ``_atoi()`` - Turns a string into an integer. Recreation of ``atoi()`` from ``<stdlib.h>``
12. [string_operations_2.c](string_operations_2.c):
  * ``word_count()`` - Counts words in a string as delimited
  * ``_strlen_const()`` - same thing as strlen, but accepts const strings.
  * ``simple_print()`` - Writes to stdout, accepts a const string.
  * ``_isdigit()`` - Checks to see if a char is a digit. Recreation of ``isdigit()`` from ``<ctype.h>``
13. [strtok.c](strtok.c):
  * ``_strchr()`` - Checks for a char in a string. Returns the string on success, and NULL on failure. Recreation of ``strchr()`` from ``<string.h>``
  * ``_strspn()`` - Gets the length of a substring. Recreation of ``strspn()`` from ``<string.h>`` with a different return type.
  * ``_strpbrk() - search a string for any set of bytes. Recreation of ``strpbrk()`` from ``<string.h>``
  * ``_strtok_r()`` - Split a string into tokens, and alters the string in the process. Recreation of ``strtok`` from ``<string.h>``
14. [AUTHORS](AUTHORS) - List of contributors.
15. [RESOURCES.md](RESOURCES.md).
16. [man_1_simple_shell](man_1_simple_shell).


## Links
For a list of resources and commands used, refer to [RESOURCES.md](RESOURCES.md)

## Authors
* **Feyitimi Victor** [LinkedIn:](http://www.linkedin.com/in/victorfeyitimi) || [Twitter](https://twitter.com/stillqlueless)
* **Mbang Benjamin** [LinkedIn](https://www.linkedin.com/in/benny-mbang-44620823b/) || [Twitter](https://twitter.com/BennyMbang)
