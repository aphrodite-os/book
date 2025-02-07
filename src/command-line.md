# Command Line

The kernel command line is in the format:

`(kernel executable name) runtime-argument1="value" runtime-argument2=123 BOOT-ARGUMENT1="value" BOOT-ARGUMENT2=456 runtime-flag BOOT-FLAG`

Where anything lowercase is an argument that can be passed at boot time or at runtime, and anything uppercase can only be passed at boot time. 

Flags are true or false values that return false if not present and true if present. Arguments can be strings or numbers, and numbers are interpreted as rust `f128`s if they have a . in them, `i128`s if they have a negative or a positive sign and no .s in them, and `u128`s otherwise. You can also add any amount of underscores to separate sections of them, however no spaces can be in them. Strings should ALWAYS be in quotes(as this is what the kernel expects and the regexes used require). Note that you can add a backslack before a single quote to have it in the string, and strings can be an arbitrary length. Flags by definition cannot have any values(any equal signs) in or by them.

All valid names should be matched by the regex(Rust-style): `[a-zA-Z-_0-9]+`

Flags are matched by the regex ` [a-zA-Z-_0-9]+ `. This ensures it doesn't match the name of the executable or arguments.

String arguments are matched by the regex ` ([a-zA-Z][a-zA-Z-_0-9]+)=('.*.+?[^\\]')(?: |$)`.

Unsigned numeric arguments are matched by the regex ` ([a-zA-Z][a-zA-Z-_0-9]+)=([0-9_]+?)(?: |$)`.

Signed numeric arguments are matched by the regex ` ([a-zA-Z][a-zA-Z-_0-9]+)=([-+][0-9_]+?)(?: |$)`.

Float arguments are matched by the regex ` ([a-zA-Z][a-zA-Z-_0-9]+)=([-+]?[0-9_]+?\.[0-9_]+?)(?: |$)`.