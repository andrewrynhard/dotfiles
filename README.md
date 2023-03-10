# Workspace

## Local Machine

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
eval "$(/opt/homebrew/bin/brew shellenv)"
brew install gnupg pinentry-mac fish yadm
yadm clone https://github.com/andrewrynhard/dotfiles.git
yadm remote set-url origin git@github.com:andrewrynhard/dotfiles.git
yadm reset --hard HEAD
yadm lfs pull
bin ensure
scp ~/.gnupg/pubring.kbx dev:~/.gnupg/
docker buildx create --bootstrap --driver docker-container --name dev --platform linux/amd64 --buildkitd-flags '--allow-insecure-entitlement security.insecure' --use ssh://dev
```
