# Environment variables

You can customize passable by using any of these environment variables:

  * PASSABLE_LENGTH: password generation length; default is 24.

  * PASSABLE_CHARACTERS: password generation characters; default is `"A-Za-z0-9~@#$%^&*(){}[]<>,./?;:-=_+"`.

  * PASSABLE_GPG_COMMAND: gpg command path; default is `gpg`.

  * PASSABLE_DECRYPT_UMASK: when decrypting to a file, use this umask; default is 0077.
