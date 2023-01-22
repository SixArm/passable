# passable: password command that's secure and simple

This is `passable`, a password command line interface tool that is secure cryptogrpahically and simple to use.


## Introdution


### Purpose

The purpose of this tool is to do three simple things:

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
sudo curl -sSL "https://raw.githubusercontent.com/SixArm/passable/master/passable" -o /usr/local/bin/passable && sudo chmod +x $_
```

If you want to verify the download, then the SHA512 is:

```
7bb9049827c09123162c15c84a5af642b99da4460dba82da577829797d2abdae2d5f971f016f6af156c9b4a08fca0b34d6c945510a3a19426e4149789f9748b7
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

Output is the decrypted text, such as the password you saved:

```txt
S&dw6[ysN@O9W5{5>^&RZ9pF
```

You can do anything you want with the decrypted text.

For example, you can copy the decrypted text to your clipboard on macOS:

```sh
echo 'S&dw6[ysN@O9W5{5>^&RZ9pF' | pbclip
```


## Test

See the repository directory `test` for some example unit tests.

The test files need to prompt you for a password; you can use any password you want.

If a test succeeds, then it will be silent.

If a test fails, then it will print an "assert" error message.

To run all the test files:

```sh
cd test
./test
```

To run one test file, for example to test the command `passable new`:

```sh
cd test/new
./test
```


## TODO

We welcome help with these todo areas:

- [ ] Improve unit tests.

- [ ] Add installation via package managers e.g. apt, brew, yum.

- [ ] Add CI/CD build process.

- [ ] Add GitHub release tags.


## Documentation

* [More examples](doc/more_examples.md)
* [FAQ inclusing comparisons with other password store managers](doc/faq.md)
* [Environment variables for customization](doc/environment_variables.md)
* [Technical implementation including GPG options](doc/technical_implementation.md)
* [Troubleshooting help](doc/troubleshooting_help.md)


## Thanks

Thanks for all the comments on [Hacker News](https://news.ycombinator.com/item?id=13382734), with special thanks to users [vesinisa](https://news.ycombinator.com/user?id=vesinisa), [twr](https://news.ycombinator.com/user?id=twr), [tptacek](https://news.ycombinator.com/user?id=tptacek), [txtutu](https://news.ycombinator.com/user?id=txutxu), [acqq](https://news.ycombinator.com/user?id=acqq), [throwawayish](https://news.ycombinator.com/user?id=throwawayish), [RMarcus](https://news.ycombinator.com/user?id=RMarcus), and [latchkey](https://news.ycombinator.com/user?id=latchkey).


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
  * Version: 5.1.0
  * Created: 2010-05-20
  * Updated: 2023-01-22
  * License: MIT or Apache-2.0 or GPL-2.0-or-later or contact us for custom
  * Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
  * Tracker: b48657369aada8deaffb880ae3486081
