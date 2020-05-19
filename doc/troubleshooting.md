# Troubleshooting

## TTY

If you get error messages like this:

    gpg: Inappropriate ioctl for device
    gpg: problem with the agent: Inappropriate ioctl for device
    gpg: error creating passphrase: Operation cancelled
    gpg: symmetric encryption of `[stdin]' failed: Operation cancelled

Then try this:

    $ export GPG_TTY=$(tty)


## Restart

If you get error message like this:

    gpg: WARNING: server 'gpg-agent' is older than us (2.2.6 < 2.2.7)
    gpg: Note: Outdated servers may lack important security fixes.
    gpg: Note: Use the command "gpgconf --kill all" to restart them.
    gpg: signal Interrupt caught ... exiting

Then try this:

    $ gpgconf --kill all
