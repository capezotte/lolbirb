# Lolbirb - Rainbows but with 'Awk power

A exercise in generating rainbows with standard Unix tools.

Should be a drop-in replacement for lolcat (but see caveats below).

Requires:
 - Terminal that supports true-color ANSI escape code (i.e `\e[38;5;R;G;Bm`)
 - /dev/fd/n
 - sh
 - awk (`gawk` is recommended - and prioritized by the script - due to better UTF-8 handling).

## Caveats

- It will always output a trailing newline.
- No long options.
- No random number generation. It'll try to tap into bash's `$RANDOM` variable, but if it's not available, the script will always output the same colors. The `-S` option can be used, though. For example, `lolbirb -S $(shuf -i0-256 -n1) -`.
