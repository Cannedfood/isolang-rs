ISO 639 language codes
======================

Introduction
------------


When dealing with different language inputs and APIs, different standards are used to identify
a language. Converting between these in an automated way can be tedious. This crate provides an
enum which supports conversion from 639-1 and 639-3 and also into these formats, as well as
into English names.

This crate contains the ISO 639 table in statically embedded tables. This is
possibly large, but can outweight the benefits, when handling different language
code formats, e.g. when handling API data from Wikipedia and FreeDict.

Conditional compilation to reduce code size is not supported at the moment.

This crate is licensed under the Apache 2.0 license, please see LICENSE.md for
the details.

## Use

Cargo.toml:

```
[dependencies]
isolang = { "git" = "https://github.com/humenda/isolang-rs" }
```

## Example

```
use isolang::Language;

assert_eq!(Language::from_639_1("de").unwrap().to_name(), "German");
assert_eq!(Language::from_639_3("spa").unwrap().to_639_1(), Some("es"));
```


