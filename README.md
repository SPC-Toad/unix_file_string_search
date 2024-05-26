# Finds - A Powerful File Search Tool

## Overview

"Finds" is a powerful command-line tool designed to search for a specified string within files and directories. It extends the basic string search functionality to support regular expressions with specific control characters for more flexible and complex search patterns.

## Demo Video
https://github.com/SPC-Toad/unix_file_string_search/assets/111462911/2fef6e83-85e8-4305-b668-d1192d150246

## Features

- **Basic String Search**: Searches for any alphanumerical string in files and directories.
- **Regular Expression Support**: Extends the basic search with support for the following control characters:
  - `.` : Matches any single alphanumerical character.
  - `*` : Matches zero or more instances of the previous character.
  - `?` : Matches zero or one instance of the previous character.
  - `()` : Non-nested parentheses for grouping substrings. Can be used to specify groups that occur zero or more times `(*)` or zero or one time `(?)`.

## Control Characters

- `.` : Matches any single alphanumerical character in a sequence. For example, "a.b" matches "aab", "a9b", etc.
- `*` : Matches zero or more instances of the previous character. For example, "a*b" matches "b", "ab", "aab", etc.
- `?` : Matches zero or one instance of the previous character. For example, "a?b" matches "ab" or "b".
- `()` : Used for grouping substrings. For example, "a(bc)*" matches "a", "abc", "abcbc", etc. Note that only non-nested parentheses are supported.

## Command-Line Arguments

The "finds" program accepts several command-line arguments as follows:

```bash
finds -p pathname [-f c|h|S] [-l] -s s
```

- `-p pathname`: Specifies the starting directory for the search.
- `-f c|h|S`: Optional flag to specify file suffixes (`c`, `h`, `S`) to search. If not specified, all regular files are searched.
- `-l`: Optional flag to include symbolic links in the search.
- `-s s`: Specifies the search string or regular expression.

## Compilation

To compile the project, navigate to the project directory and run:

```bash
make
```

This will compile the source files and generate the executable.

## Usage

The basic usage of the "finds" tool is as follows:

```bash
./finds -p pathname [-f c|h|S] [-l] -s searchstring
```

- `pathname`: The directory path where the search will be performed.
- `searchstring`: The string or regular expression to search for.

## Example

```bash
./finds -p /path/to/directory/or/file -f c -s "a*b"
```

This command will search for any occurrences of "a*b" in `.c` files within the specified directory, matching patterns like "ab", "aab", etc.

## Traversing a Directory Tree

Starting with the directory specified by `pathname`, the program inspects all subsequent directory entries. For each regular file (and symbolic link if `-l` is specified), the program opens it and searches for the presence of `s`. If `s` is found, the line containing the string is printed to the standard output, followed by the full name of the file.

## Output

All output is written to the standard output device. Appropriate error messages appear on standard error where necessary, but the functions continue execution when any errors are non-fatal.

## Want to view how I implemented it?
    Please contact me seperately. I will give you access to my private repository where the code is. 

        - Please inform me who you are and why you want to access it. Thank you!
