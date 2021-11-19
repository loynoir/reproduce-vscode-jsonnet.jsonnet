### What
When importing jsonnet, vscode jsonnet may look for percentage encoded path X instead of path X.

### Reproduce
Path contain at least one special character, eg: `@`

```txt
$ code --goto @scope/name/index.jsonnet:3:12

    b: lib.<hover>a</hover>

jsonnet language server see error:

    Error: ENOENT: no such file or directory, stat `path/to/%XXfoo/bar`
```