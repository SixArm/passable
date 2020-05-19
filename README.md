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


## Examples of more functionality

Encrypt a file then delete it:

```sh
passable encrypt example.txt && rm $_
```

Encrypt a file to a specific output file name:

```sh
passable encrypt example.txt --output foo.gpg
```

Decrypt a file then delete it:

```sh
passable decrypt example.txt.gpg && rm $_
```

Decrypt a file to a specific output file name:

```sh
passable decrypt example.txt.gpg --output foo.txt
```


## Examples of using directories

Encrypt a directory:

```sh
tar --create mydir | passable encrypt --output mydir.tar.gpg
```

Encrypt a directory then delete it:

```sh
tar --create mydir | passable encrypt --output mydir.tar.gpg && rm -rf $_
```

Decrypt a directory:

```sh
passable decrypt mydir.tar.gpg | tar -x
```

Decrypt a directory then delete it:

```sh
passable decrypt mydir.tar.gpg | tar -x && rm foo.tar.gpg
```


## Environment variables

You can customize passable by using any of these environment variables:

  * PASSABLE_LENGTH: password generation length; default is 24.

  * PASSABLE_CHARACTERS: password generation characters; default is `"A-Za-z0-9~@#$%^&*(){}[]<>,./?;:-=_+"`.

  * PASSABLE_GPG_COMMAND: gpg command path; default is `gpg`.

  * PASSABLE_DECRYPT_UMASK: when decrypting to a file, use this umask; default is 0077.



## Advice

We tend to use these naming conventions:

  * GPG file name extension `.gpg`.

  * tar file extension `.tar`.

We tend to skip compression:

  * We tend to use `gpg` without using compression.

  * We tend to use `tar` without using compression.


## Troubleshooting

### TTY

If you get error messages like this:

    gpg: Inappropriate ioctl for device
    gpg: problem with the agent: Inappropriate ioctl for device
    gpg: error creating passphrase: Operation cancelled
    gpg: symmetric encryption of `[stdin]' failed: Operation cancelled

Then try this:

    $ export GPG_TTY=$(tty)


### Restart

If you get error message like this:

    gpg: WARNING: server 'gpg-agent' is older than us (2.2.6 < 2.2.7)
    gpg: Note: Outdated servers may lack important security fixes.
    gpg: Note: Use the command "gpgconf --kill all" to restart them.
    gpg: signal Interrupt caught ... exiting

Then try this:

    $ gpgconf --kill all


## Older versions

If you use GPG v1, and you want to skip the GPG user agent, then you may want to add this option:

    --no-use-agent


## FAQ

Q. Why use `passable` instead of just GPG directly?

A. Because we work with many team members with a wide range of skill levels and on a wide range of systems. We believe that `passable` is easier to understand for our top use cases, and also provides careful compatibility such as with older systems that use GPG 1 instead of GPG 2. The `passable` command calls GPG, so the inputs and output and options are all fully GPG under the covers. You can use GPG directly as you like.

Q. Why use `passable` instead of `pass` which is also a GPG command line tool?

A. Because we want a tool that doesn't need any initialization and doesn't even need write access. You can use `passable` on any existing compatible GPG file. For comparsion, we evaluated `pass` and saw that each user would need to initiatlization, and `pass` would default to create a dot directory within a user's home directory, then write files there.

Q. Why use many GPG options instead of a simple 'gpg -c' command?

A. These options are good for GPG v1 a.k.a. GPG classic. GPG v1 has stranger defaults than GPG v2. The default ciphers are CAST5, (very slow) compression is on by default, hashes are RIPEMD. The defaults are a bit obscure and very slow: something like two dozen MB/s encryption/decryption speed, on a machine that can do AEAD at 2.5-4 GB/s (AES-GCM or Chapoly). A large part of that is the compression (zlib-ish I think), though. Credit: users accqq and throwawayish [here](https://news.ycombinator.com/item?id=13382734)


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
