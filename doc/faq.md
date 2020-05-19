# FAQ

## Q. Why use `passable` instead of other password store managers, such as 1Password, LastPass, Bitwarden, etc.?

A. Because `passable` is free open source, simple to prove secure, command line friendly, and can work with any other program. For some teams we do use 1Password, LastPass, Bitwarden, and other passsword store managers, and we like all of them. Yet for some of our teams and clients, we like to also use `passable` because it's so simple.

## Q. Why use `passable` instead of the `pass` password store manager, which is also a GPG command line tool?

A. Because `passable` is even simpler. It doesn't need any initialization, and doesn't need write access. You can use `passable` on any existing compatible GPG file. For some teams we dp use `pass`, and we like it for storing per-user passwords, such having each user do their own initiatlization to create a hidden dot directory and then write files there.

## Q. Why use `passable` instead of just GPG directly?

A. Because `passable` is simpler for many people to learn and use. We work with many teams, with a wide range of skill levels, and on a wide range of systems. We believe that `passable` is easier to understand for our top use cases, and provides compatibility with older systems that use GPG 1 instead of GPG 2. 

## Q. Is `passable` compatible with GPG?

A. Yes `passable` calls GPG. The `passable` inputs, outputs, and options are all fully GPG under the covers. For example, you can freely intermix `passable` commands and GPG commands, all on the same files.

## Q. Why use many GPG options instead of a simple 'gpg -c' command?

A. These options are good for GPG v1 a.k.a. GPG classic. GPG v1 has stranger defaults than GPG v2. The default ciphers are CAST5, (very slow) compression is on by default, hashes are RIPEMD. The defaults are a bit obscure and very slow: something like two dozen MB/s encryption/decryption speed, on a machine that can do AEAD at 2.5-4 GB/s (AES-GCM or Chapoly). A large part of that is the compression (zlib-ish I think), though. Credit: users accqq and throwawayish [here](https://news.ycombinator.com/item?id=13382734)
