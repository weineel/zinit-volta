# null

**Note: zinit and zplugin are different names of the same thing**

An empty repository to aid zplugin's hooks-hacks. You can fork it to have a private copy of it :)

Example uses:

When what's needed is an atclone'' hook to e.g. install a software (plus atpull'' hook to update it):

```
# The invocation uses https://github.com/zdharma-continuum/null repo as a placeholder
# for the atclone'' and atpull'' hooks
# run-atpull：Even if this repository has not been updated, atpull will still be executed during `zinit update weineel/zinit-volta`.

zinit ice as"program" pick"volta" \
    atclone"curl https://get.volta.sh | bash" \
    atpull"curl https://get.volta.sh | bash -s -- --skip-setup" \
    run-atpull \
    atload'export VOLTA_HOME="$HOME/.volta" && export PATH="$VOLTA_HOME/bin:$PATH"'
zinit light weineel/zinit-volta
```
