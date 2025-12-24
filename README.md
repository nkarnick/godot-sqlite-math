This is a fork of https://github.com/2shady4u/godot-sqlite enabling the sqlite math functions as outlined in the readme:



### 5. Does this plugin support the XYZ Extension of SQLite?

Following SQLite extensions are supported by this plugin, although they require the user to re-compile the plugin:

| Extension                                                                    | flag                  | default |
|------------------------------------------------------------------------------|-----------------------|---------|
| [SQLite FTS5 Extension](https://sqlite.org/fts5.html)                        | enable_fts5           | no      |
| [Built-In Mathematical SQL Functions](https://sqlite.org/lang_mathfunc.html) | enable_math_functions | no      |

To re-compile the plugin with XYZ enabled, follow the instructions as defined in the 'How to contribute?'-section below.  
Depending on your choice, following modifications have to be made:


#### Using Github Actions

Update the `common_flags`-field of the `.github/workflows/build_var.json`-file, as follows:

```json
"common_flags": "enable_math_functions=no"
```

```json
"common_flags": "enable_math_functions=yes"
```

Afterwards, push a new commit (containing this change) to the `master`-branch of your forked remote. This commit triggers a new workflow that re-compiles the plugin's binaries with FTS5 enabled.

