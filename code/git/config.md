# config

## Config Levels

This is for unixish systems (aka Not Windows)

```bash
$(prefix)/etc/gitconfig # system-wide
~./gitconfig            # 'global config' for current user
.git/config             # config for current repo/ folder
```

## Set config for specific file

```bash
git config --file <file_name> user.name "[name]"
```

you can also set the username for each file in `.git/config` by modifying the following:

```
[remote "origin"]
    url = https://github.com/GeorgeIpsum/gitbook.git
```

to

```
[remote "origin"]
    url = https://<USERNAME>@github.com/GeorgeIpsum/gitbook.git
```

asdf
