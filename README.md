# pgl_types

[![Package Version](https://img.shields.io/hexpm/v/pgl_types)](https://hex.pm/packages/pgl_types)
[![Hex Docs](https://img.shields.io/badge/hex-docs-ffaff3)](https://hexdocs.pm/pgl_types/)

## Supported types

- `bool`
- `oid`
- `int2`
- `int4`
- `int8`
- `float4`
- `float8`
- `text`
- `varchar`
- `name`
- `char`
- `bytea`
- `time`
- `date`
- `timestamp`
- `timestamptz`
- `interval`
- `array`

## TODO

- [ ] Nested `array` encoding
- [ ] More types

```gleam
import pgl/types
import pgl/value

pub fn main() -> Nil {
  let int4_type_info = get_type_info("int4")

  // Encode an integer as int4
  let assert Ok(encoded) = types.encode(10, int4_type_info, with: types.int4)

  // Decode a bit array as an int4 into a dynamic value
  let assert Ok(int_dynamic) = types.decode(encoded, int4_type_info)

  // Create a list of `value.Value`s
  let params = [value.int(10), value.null, value.text("text")]
}
```

Further documentation can be found at <https://hexdocs.pm/pgl_types>.

## Installation

TODO

## Development

```sh
gleam run   # Run the project
gleam test  # Run the tests
```

## Acknowledgements

Much thanks to [`pg_types`](https://github.com/tsloughter/pg_types) for encoding and decoding logic.
