
# bytesize

Provides a function to print quantities of bytes in human-readable formats.

Allows you to choose precision (number of decimals) and whether you would 
prefer IEC or SI units (binary or base 10).

Modeled on strconv and the FormatInt / FormatFloat functions:

    bytesize.FormatBytes(value int, base int, precision int) string

Examples:

    bytesize.FormatBytes(1024, 2, 1) = "1.0KiB"
    bytesize.FormatBytes(2000000, 10, 2) = "2.00MB"

See also:

 * https://en.wikipedia.org/wiki/Binary\_prefix
 * http://lpar.ath0.com/2008/07/15/si-unit-prefixes-a-plea-for-sanity/ 

## Rationale

While "Effective Go" has sample code for a ByteSize type, it has a number of
problems:

 1. It doesn't support variable precision, and always returns two decimals.
 2. It gets the units wrong, using SI prefixes for binary units.
 3. It doesn't let you choose between SI and IEC units.
 4. It requires that you cast your quantities to ByteSize type.

## License

BSD-style.

