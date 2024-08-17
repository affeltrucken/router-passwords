Guide for reading passwords patterns:
?l - Lowercase letter (a-z)
?u - Uppercase letter (A-Z)
?d - Digit (0-9)
?s - Special character (e.g., !, @, #, etc.)
?a - Any alphanumeric character (lowercase, uppercase, digit, special)

These can be combined, for example:

?ld?ld?ld?ld?ld?ld?ld?ld

for lowercase or digit for each character.

All characters in curly brackets in ROUTER-NAME column
indicate where the unique string for each router is.

For example: Tele2_F4812B
Would be:    Tele2_{XXXXXX}

| BRAND | WLAN-ROUTER-NAME | WLAN-PASSWORD-PATTERN | LENGTH | COMMENT | # OF HASHES |
|---|---|---|---|---|---|
| Tele2 | Tele2_{XXXXXX} | ?ld?ld?ld?ld?ld?ld?ld?ld | 8 | ~1 month to crack @ 380 000 HPS (RTX 2060)  | 1 015 599 608 640 |
| TP-Link | TP-Link_{XXXX} | ?d?d?d?d?d?d?d?d | 8 | Cracked in less than a minute | 10 000 000 |
| Tre | 3Bredband-{XXXX} | ?a?a?a?a?a?a?a?a?a?a | 10 | Don't even bother | 839 299 365 868 340 224 |
| Com Hem | COMHEM_{XXXXXX} | ?l?l?l?l?l?l?l?l | 8 | ~6 days to crack @ 380 000 | 208 827 064 576 |
| Telia | Telia-{XXXXXX} | ?du?du?du?du?du?du?du?du?du?du | 10 | ~110 days | 3 656 158 440 062 976 |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
