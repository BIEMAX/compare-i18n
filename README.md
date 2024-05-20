# compare-i18n
is a tool designed to assist developers and translators in managing and comparing internationalization (i18n) files across different translation files.

[!Logs as tables](./imgs/1.png)

## Requirements

- NodeJS or BunJs

## Supported Files

| Extension | Supported |
| --   | -- |
| JSON | ✅ |
| JS   | ✅ |
| INI  | ❌ |
| XML  | ❌ |

## Supported Structures

JavaScript object:
```javascript
export default {
    my: {
        custom: {
            property: 'my-value'
        }
    }
}
```

Nested Json object:
```json
"my.custom.property": "my-value",
```

Flattened Json object:
```json
"my": {
    "custom": {
        "property": "my-value"
    }
}
```

## Rules

1. The files need be named using the language code (`pt, es, us`).
2. It's necessary to define a language to be used as model, to check if in the other translations has all mandatory keys (`considering the default language as model`)
3. Will ignore comments (`in the case JS Objects`) and empty lines
4. It was not fully tested, issues can be found.


## How to run:

1. Copy script into your project folder.
2. Run with the command: 
```bash
# With NodeJs:
node index.js

# Or with BunJjs:
bun run index.js
```
3. Will request the following information to continue.
```bash
1. Folder with translations (default: './src/i18n/'): 
2. Language to be used as example (default: pt): 
3. Show the missing keys as table (default: true):
```

4. Will print a table or in the `console.log` the missing keys in other translations files.