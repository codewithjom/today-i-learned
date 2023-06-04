# Chown Command: Change Owner of File in Linux

Linux Chown Command Syntax

```sh
chown [OPTIONS] USER[:GROUP] FILE(S)
```

- [OPTIONS] - the command can be used with or without additional options.
- [USER] - the username or the numeric user ID of the new owner of a file.
- [:] - use the colon when changing a group of a file.
- [GROUP] - changing the group ownership of a file is optional.
- FILE - the target file.

# How to check ownership of a file in Linux

```sh
ls -l
```

# How to change the owner of a file

Assume that you have a username `test` and a file `sample` which is owned by root.

```sh
chown test sample
```
