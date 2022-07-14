# GitHub

## SSH Config

```
##########################
# Personal               #
##########################
Host GitHub
        User git
        Hostname github.com
        AddKeysToAgent yes
        IdentityFile ~/.ssh/<your private key>
```

if `gh clone <repo>` don't work.
Need to use following:
`gh config set git_protocol https -h github.com`
or
`git clone https://github.com/user/repo.git`

## Mac OS

use `eval "$(ssh-agent -s)` to check ssh-agent is running
To add private key to SSH, use `ssh-add --apple-use-keychain ~/.ssh/<your private key>`

## Create Repository on GitHub

use the command below to list all repos on GitHub:
`gh repo list`

use the command below to create a new repo and push locally committed to repo
`gh repo create <repo name> --public --description="<repo descr>"`
`git push origin master --verbose`

To clone the latest from the repo
`gh repo clone user/repo "--depth 1 --recurse-submodules --shallow-submodules"`
`git clone --depth 1 --recurse-submodules --shallow-submodules https://github.com/user/repo.git`
