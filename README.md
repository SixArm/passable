# passable: password store command that's just good enough

This is `passable`, a simple password store tool, also known as a password manager, a secret keeper, or a file valut.


## Introdution


### Purpose

The purpose of this tool is to be just good enough to do three things:

* Create a new password.

* Encrypt a file.

* Decrypt a file.


### Usage

Syntax:

```sh
passable new
passable encrypt <file>
passable decrypt <file>
```


### Installation

Download the program `passable` anywhere you want, and make it runnable.

Example on typical macOS and Linux:

```sh
sudo curl -sSL "https://raw.githubusercontent.com/SixArm/passable/master/passable" -o /usr/local/bin/passable && chmod +x $_
```


## Examples


### Create a new password

Command:

```sh
passable new
```

Output is a new strong secure password:

```txt
S&dw6[ysN@O9W5{5>^&RZ9pF
```

You can do anything you want with the new password.

For example, you can save the new password as a new file:

```sh
echo 'S&dw6[ysN@O9W5{5>^&RZ9pF' > file.txt
```


### Encrypt a file

Command:

```sh
passable encrypt file.txt
```

Output is a new encrypted file `file.txt.gpg`.

You can do anything you want with the new encrypted file.

For example, you can add the new encrypted file to git version control:

```sh
git add file.txt.gpg
```


### Decrypt a file

Command:

```sh
passable decrypt file.txt.gpg
```

Output is the decrypted text, such as the password yuu saved:

```txt
S&dw6[ysN@O9W5{5>^&RZ9pF
```

You can do anything you want with the decrypted text.

For example, you can copy the decrypted text to your clipboard on macOS:

```sh
echo 'S&dw6[ysN@O9W5{5>^&RZ9pF' | pbclip
```


## Documentation

* [More examples](doc/more_examples.md)
* [FAQ inclusing comparisons with other password store managers](doc/faq.md)
* [Environment variables for customization](doc/environment_variables.md)
* [Technical implementation including GPG options](doc/technical_implementation.md)
* [Troubleshooting help](doc/troubleshooting_help.md)


## Thanks

Thanks for all the comments on [Hacker News](https://news.ycombinator.com/item?id=13382734), with special thanks to users [vesinisa](https://news.ycombinator.com/user?id=vesinisa), [twr](https://news.ycombinator.com/user?id=twr), [tptacek](https://news.ycombinator.com/user?id=tptacek), [txtutu](https://news.ycombinator.com/user?id=txutxu), [acqq](https://news.ycombinator.com/user?id=acqq), [throwawayish](https://news.ycombinator.com/user?id=throwawayish), [RMarcus](https://news.ycombinator.com/user?id=RMarcus)


## See also
 
These commands are similar:

  * [`gpg-encrypt`](https://github.com/SixArm/gpg-encrypt): 
    use GPG to encrypt a file using our best settings.
  
  * [`gpg-decrypt`](https://github.com/SixArm/gpg-decrypt): 
    use GPG to decrypt a file using our best settings.

  * [`openssl-encrypt`](https://github.com/SixArm/openssl-encrypt): 
    use OpenSLL to encrypt a file using our best settings.
  
  * [`openssl-decrypt`](https://github.com/SixArm/openssl-decrypt): 
    use OpenSSL to decrypt a file using our best settings.
 
 
## Tracking

  * Command: passable
  * Website: https://sixarm.com/passable
  * Cloning: https://github.com/sixarm/passable
  * Version: 5.0.0
  * Created: 2010-05-20
  * Updated: 2020-05-20
  * License: GPL
  * Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
  * Tracker: b48657369aada8deaffb880ae3486081
