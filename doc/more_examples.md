# More examples of more functionality


## Encrypt a file

Encrypt a file then delete it:

```sh
passable encrypt example.txt && rm $_
```

Encrypt a file to a specific output file name:

```sh
passable encrypt example.txt --output foo.gpg
```


## Decrypt a file

Decrypt a file then delete it:

```sh
passable decrypt example.txt.gpg && rm $_
```

Decrypt a file to a specific output file name:

```sh
passable decrypt example.txt.gpg --output foo.txt
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
