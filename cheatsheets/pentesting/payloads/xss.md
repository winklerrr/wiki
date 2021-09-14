# XSS Payloads

## Obfuscation

Some sites make use of string filters to "detect" xss attacks. For example, they scan the input for string containing keywords like `script` or even `alert`
(the later one is kinda funny, as it's more used for reconnaissance and blocking only this would still allow to hack a site, lol).



| Keyword   | Obfuscation                        | Explanation                                                                                        |
|-----------|------------------------------------|----------------------------------------------------------------------------------------------------|
| `alert`   | `top[8680439..toString(30)](1337)` | first dot is recognized as decimal point, second dot is then recognized as invoking call to object, all to the base of `30` (numbers `0`..`9` + first 20 letters of the alphabet (`t`) |
