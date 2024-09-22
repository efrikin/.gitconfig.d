# `.gitconfig.d`

Configuration files for `git`

## `Installing`

```bash
git clone https://github.com/efrikin/.gitconfig.d.git
git config --global include.path "~/.gitconfig.d/00-main"
```

### `References`

- [git-config: include](https://git-scm.com/docs/git-config#_includes)
- `man git-config`

## `Configuration`

```bash
git config set -f ~/.gitconfig.d/01-user user.name "Your Name"
git config set -f ~/.gitconfig.d/01-user user.email "you@example.com"
```

### `Ignoring ~/.gitconfig.d/01-user`

```bash
git update-index --assume-unchanged 01-user
```

### `References`

- [git-update-index: using "assume unchanged" bit](https://git-scm.com/docs/git-update-index#_using_assume_unchanged_bit)
- `man git-update-index`

## `Usage`

### `git tag/commit signinig/verifying`

> To verify signatures, we also need to tell Git what SSH public keys are trusted for verification.

**ssh public key must be added to ~/.gitconfig.d/allowed_signers and GitHub profile**

#### `Signing`

```bash
git commit -m 'Init'
git tag -s 1.0.0 -m 'Init'
```

#### `Verifying`

```bash
git log --oneline --show-signature
git show 1.0.0
git tag -v 1.0.0
```

### `References`

- [Yubikey: Securing Git with SSH and FIDO security keys](https://developers.yubico.com/SSH/Securing_git_with_SSH_and_FIDO2.html)
- [allowed signers: file format](https://man.openbsd.org/ssh-keygen#ALLOWED_SIGNERS)

