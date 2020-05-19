# passable: password store command that's just good enough

This is `passable`, a simple password store tool, also known as a password manager, a secret keeper, or a file valut.

The purpose of this tool is to be just good enough to do three things:

* Create a new password.

* Encrypt a file.

* Decrypt a file.

Syntax:

```sh
passable new
passable encrypt <file>
passable decrypt <file>
```

This tool uses the command line interface, GNU Privacy Guard (GPG), and settings that make the encryption more-compatible on many systems including older systems.


## Install

Download the program `passable` anywhere you want, and make it runnable.

Example on typical macOS and Linux:

```sh
sudo curl -sSL "https://raw.githubusercontent.com/SixArm/passable/master/passable" -o /usr/local/bin/passable && chmod +x $_
```

We welcome help creating system installation packages for various platforms.


## Examples

Create a new password:

```sh
passable new
```

Output is a new strong secure password.

Encrypt a file:

```sh
passable encrypt example.txt
```

Output is a new encrypted file `example.txt.gpg`.

Decrypt a file:

```sh
passable decrypt example.txt.gpg
```

Output is the decrypted text.


## Examples of using the clipboard

Decrypt a file to the clipboard on macOS:

```sh
passable decrypt example.txt.gpg | pbcopy
```

Decrypt a file to the clipboard on Linux:

```sh
passable decrypt example.txt.gpg | xclip
```



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
