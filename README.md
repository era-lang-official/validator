# Era Validator (`github.com/era-lang-official/validator`)

Declarative input validation and constraint checking library for Era.

## Features
- **Field Predicates**: `is_email`, `is_numeric`, `is_alphanumeric`, `is_ipv4`, `in_range`.
- **Length Constraints**: `min_length`, `max_length`.
- **SchemaValidator**: Multi-rule aggregator producing structured error reports.

## Usage
```era
import "github.com/era-lang-official/validator";

fn main() {
    let mut v = SchemaValidator::new();
    v.require_email("contact".to_string(), "admin@era.org".to_string());
    v.require_min_len("pwd".to_string(), "supersecret".to_string(), 8);
    let r = v.report();
    assert(r.is_valid);
}
```

