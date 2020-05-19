# More examples of more functionality


## Encrypt a file

Encrypt a file then delete it:

```sh
passable encrypt file.txt && rm $_
```

Encrypt a file to a specific output file name:

```sh
passable encrypt file.txt --output foo.gpg
```


## Decrypt a file

Decrypt a file then delete it:

```sh
passable decrypt file.txt.gpg && rm $_
```

Decrypt a file to a specific output file name:

```sh
passable decrypt file.txt.gpg --output foo.txt
```


## Decrypt a file to the clipboard on macOS

Command:

```sh
passable decrypt file.txt.gpg | pbcopy
```


## Decrypt a file to the clipboard on Linux

Decrypt a file to the clipboard on Linux:

```sh
passable decrypt file.txt.gpg | xclip
```


## Encrypt a diretory

Encrypt a directory:

```sh
tar --create mydir | passable encrypt --output mydir.tar.gpg
```

Encrypt a directory then delete it:

```sh
tar --create mydir | passable encrypt --output mydir.tar.gpg && rm -rf $_
```

## Decrypt a directory

Decrypt a directory:

```sh
passable decrypt mydir.tar.gpg | tar -x
```

Decrypt a directory then delete it:

```sh
passable decrypt mydir.tar.gpg | tar -x && rm foo.tar.gpg
```
