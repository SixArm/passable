# FAQ

## Q. Why use `passable` instead of just GPG directly?

A. Because we work with many team members with a wide range of skill levels and on a wide range of systems. We believe that `passable` is easier to understand for our top use cases, and also provides careful compatibility such as with older systems that use GPG 1 instead of GPG 2. The `passable` command calls GPG, so the inputs and output and options are all fully GPG under the covers. You can use GPG directly as you like.

## Q. Why use `passable` instead of `pass` which is also a GPG command line tool?

A. Because we want a tool that doesn't need any initialization and doesn't even need write access. You can use `passable` on any existing compatible GPG file. For comparsion, we evaluated `pass` and saw that each user would need to initiatlization, and `pass` would default to create a dot directory within a user's home directory, then write files there.

## Q. Why use many GPG options instead of a simple 'gpg -c' command?

A. These options are good for GPG v1 a.k.a. GPG classic. GPG v1 has stranger defaults than GPG v2. The default ciphers are CAST5, (very slow) compression is on by default, hashes are RIPEMD. The defaults are a bit obscure and very slow: something like two dozen MB/s encryption/decryption speed, on a machine that can do AEAD at 2.5-4 GB/s (AES-GCM or Chapoly). A large part of that is the compression (zlib-ish I think), though. Credit: users accqq and throwawayish [here](https://news.ycombinator.com/item?id=13382734)
