<!--
© 2018, PolySync Technologies, Inc., Devin Smith <dsmith@polysync.io>

This file is part of Howser

Howser is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

Howser is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with Howser.  If not, see <http://www.gnu.org/licenses/>.
-->

# Howser

## Overview

Howser is a command line tool for verifying document conformance via the [rx spec](https://github.com/PolySync/rx).
If your organization frequently produces Markdown documentation, and it would be nice to ensure that all that 
documentation contained certain shapes of things without having to go through it all by hand, then this is the tool for 
you. For instance, you could use Howser as part of a build system to verify that all your projects have 
sensible README files and consistently formatted requirements documentation.

## Getting Started

### Dependencies

* [libcmark](https://github.com/commonmark/cmark#installing)

### Building

`cargo build`

`cargo install`

## Usage

`howser [FLAGS] [SUBCOMMAND]`

***Flags***

* `-h, --help` Prints help information
* `-V, --version` Prints version information
* `-v, --verbose` Uses verbose (multi-line) output for errors and warnings.

***Subcommands***

* `check <Filename>` Checks that a document intended for use as a prescription conforms to the Rx spec.  
* `validate <Prescription> <Document>` Perform validation of a Markdown document against an Rx prescription file.
* `help <Subcommand>` Print out help information on a subcommand.

### Examples

`howser check template.rx`.

> Checks the file named `template.rx` for conformance to the Rx spec.

`howser validate template.rx document.md`

> Validates the contents of `document.md` against the prescription file `template.rx`.

## Tests

Howser contains both unit tests and property based tests. The unit tests provide coverage for application logic and
certain specific document validation scenarios while the property based tests target broad coverage coverage of 
arbitrarily generated validation scenarios.

### Running Tests

`cargo test`

# License

© 2018, PolySync Technologies, Inc., Devin Smith <dsmith@polysync.io>

[GPL version 3](https://github.com/PolySync/howser/blob/master/LICENSE)