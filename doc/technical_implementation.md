# Technical implemention

## Encryption settings

We use these choices:

  * Symmetric encryption, i.e. we use the same password for encryption and decryption.
    We choose this because our users can understand symmetric more easily than asymmetic.

  * Encryption using the aes256 cipher algorithm.
    We choose this because it's a good balance of strong, fast, and portable.

  * Digesting using the sha256 digest algorithm.
    We choose this because it's a good balance of strong, fast, and portable.

  * No compression, because typically our files are small or already compressed.
    We choose this to maximize portability, PGP compatibility, and speed.

  * Explicit settings, rather than depending on defaults.

  * Suitable for GPG v2; backwards-compatible with GPG v1 when possible.

To get our settings, we use these gpg options:

  * `--symmetric`:                   Encrypt with symmetric cipher only This command asks for a passphrase.

  * `--cipher-algo aes256`:          Use AES256 as the cipher algorithm

  * `--digest-algo sha256`:          Use SHA256 as the digest algorithm.

  * `--cert-digest-algo sha256`:     Use SHA256 as the message digest algorithm used when signing a key.

  * `--compress-algo none -z 0`:     Do not compress the file.

  * `--s2k-mode 3`:                  Use passphrase mangling iteration mode.

  * `--s2k-digest-algo sha256`:      Use SHA256 as the passphrase iteration algorithm.

  * `--s2k-count 65011712`:          Use the maximum number of passphrase iterations.

  * `--force-mdc`:                   Use modification detection code.

  * `--quiet`:                       Try to be as quiet as possible.

  * `--no-greeting`:                 Suppress the initial copyright message but do not enter batch mode.

  * `--pinentry-mode=loopback`       Use the terminal for PIN entry.

Encrypt command:

```sh
gpg \
--symmetric \
--cipher-algo aes256 \
--digest-algo sha256 \
--cert-digest-algo sha256 \
--compress-algo none -z 0 \
--s2k-mode 3 \
--s2k-digest-algo sha256 \
--s2k-count 65011712 \
--force-mdc \
--quiet --no-greeting \
--pinentry-mode=loopback \
"$@"
```

## Decryption settings

To get our settings, we use these gpg options:

  * `--quiet`: Try to be as quiet as possible.

  * `--no-greeting`: Suppress the initial copyright message but do not enter batch mode.

If you are on an older system, then you may want to add this:

  * `--no-use-agent`: Do not use a system agent such as Ubuntu's gnome-keyring process.

  * `--pinentry-mode=loopback`: Use the terminal for PIN encry.

Decrypt command:

```sh
gpg \
--decrypt \
--quiet \
--no-greeting \
--pinentry-mode=loopback \
"$@"
```

## Optional GPG configuration settings

If you prefer to use GPG configuration setting, 
here's how to do it using the file `.gnupg/gpg.conf`:

```conf
personal-cipher-preferences AES256 AES
personal-digest-preferences SHA256 SHA512
personal-compress-preferences Uncompressed
default-preference-list SHA256 SHA512 AES256 AES Uncompressed

cert-digest-algo SHA256

s2k-cipher-algo AES256
s2k-digest-algo SHA256
s2k-mode 3
s2k-count 65011712

disable-cipher-algo 3DES
weak-digest SHA1
force-mdc
```

Note that these options impact compatibility with other GPG/PGP clients.

Credit: User twr [here](https://news.ycombinator.com/item?id=13382734)


## Naming conventions

We tend to use these naming conventions:

  * GPG file name extension `.gpg`.

  * tar file extension `.tar`.


## Compression

We tend to skip compression:

  * We tend to use `gpg` without using compression.

  * We tend to use `tar` without using compression.


## Older versions

If you use GPG v1, and you want to skip the GPG user agent, then you may want to add this option:

    --no-use-agent

