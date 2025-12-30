# Swedish ISP Router Wordlist Masks & Target Profiles

A collection of default WPA2/WPA3 password patterns for common routers and ISPs in Sweden. This data is intended for security research, penetration testing, and password recovery.

## Disclaimer
This repository is for **educational and authorized security testing purposes only**. Unauthorized access to networks you do not own or have explicit permission to test is illegal.

## Hashcat Mask Legend
The patterns below use standard Hashcat mask syntax.

* **`?l`** = Lowercase letter (a-z)
* **`?u`** = Uppercase letter (A-Z)
* **`?d`** = Digit (0-9)
* **`?s`** = Special character
* **`?a`** = Alphanumeric (a-z, A-Z, 0-9, special)
* **`-1`** = Custom Charset (Defined in the command)

## Target Profiles

All characters in **`{curly brackets}`** in the **Router Name** column indicate where the unique string for each router is located.

| ISP / Brand | SSID Pattern | Password Logic (Human Readable) | Length | Hashcat Mask (Syntax) | Est. Difficulty |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TP-Link** | `TP-Link_{XXXX}` | 8 Digits | 8 | `?d?d?d?d?d?d?d?d` | **Instant** (<5m) |
| **Tele2** | `Tele2_{XXXXXX}` | Lowercase + Digits (Base36) | 8 | `-1 ?l?d ?1?1?1?1?1?1?1?1` | **High** (Weeks) |
| **Tele2 / ComHem** | `COMHEM_{XXXXXX}` | Lowercase + Digits (Hex)* | 8 | `-1 ?dabcdef ?1?1?1?1?1?1?1?1` | **Medium** (Hours) |
| **Telia** | `Telia-{XXXXXX}` | Uppercase + Digits (Hex) | 10 | `-1 ?u?d ?1?1?1?1?1?1?1?1?1?1` | **Hard** (Days) |
| **Tre (3)** | `3Bredband-{XXXX}` | Alphanumeric (Mixed Case) | 10 | `-1 ?l?u?d ?1?1?1?1?1?1?1?1?1?1` | **Extreme** (Years) |
| **Bredband2** | `Bredband2-{XXXX}` | Uppercase + Digits | 14 | `-1 ?u?d ?1?1?1?1...` (x14) | **Impossible** |
| **Zyxel** | `Zyxel_XXXX` | Lower + Upper + Digit | 13 | `?a?a?a...` (x13) | **Impossible** |

*> **Note on Tele2/ComHem:** Many Sagemcom routers use Hexadecimal (0-9, a-f) rather than full alphanumeric. If no letters past 'f' are observed, use the Hex mask for significantly faster cracking.*

## Usage Example

To run a specific attack pattern using Hashcat (e.g., for Tele2 Hex):

```bash
# Define custom charset 1 as digits + a,b,c,d,e,f
hashcat -m 22000 capture.hc22000 -a 3 -1 ?dabcdef ?1?1?1?1?1?1?1?1
```
