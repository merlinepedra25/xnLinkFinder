## Changelog

- v1.1

  - New
    - Created this CHANGELOG.md file!
    - Add .gitignore file to exclude output.txt
    - Added functionality to allow output to be piped to another program. The output file will still be written. Errors and progress bar are written to STDERR
    - Added functionality to allow input to br piped to xnLinkFinder. A Burp or ZAP file cannot be piped and must use `-i` for these.
  - Changed
    - Fixed a bug that gets an incorrect number of responses in a ZAP file if the is binary image data in the file. The `grep` statement used has to use the `--text` argument.
    - Do a hard exit if someone keeps pressing Ctrl-C
    - Links were only being prefixed with `-sp` value if the found link started with `/`. Now, a link will be prefixed if it doesn't start with http, or the domain or prefix, in case we miss out on a valid link. For example, if `-sp http://exmaple.com` was used and link `index.html` was found, it wasn't prefixed before and just returned as `index.html`. Now it will be returned as `http://exmaple.com/index.html`.
    - Fixed a bug where Header, and therefore ContentType, wasn't correctly retrieved for responses in an OWASP ZAP file.
    - A few minor tweaks here and there!
