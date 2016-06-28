# Mortadelo CLI tool

`THIS TOOL IS UNDER HEAVY DEVELOPMENT`

### What for?

Mortadelo makes assming AWS roles pretty simple, asking for temporary AWS credentials and dumping them to `~/.aws/credentials`

### Installation

```
wget https://github.com/ivanfoo/mortadelo/releases/download/v0.1.0/mortadelo_v0.1.0.tgz
tar -xfv mortadelo_v0.1.0.tgz
cp mortadelo /usr/local/bin/
```

### How to use it

```
Usage:
  mortadelo [OPTIONS] <assume | clean | configure>

Help Options:
  -h, --help  Show this help message

Available commands:
  assume     assume role
  clean      clean generated files
  configure  configure roles alias file
```

**Using an explicit arn role:**

`mortadelo assume -r arn:aws:iam::xxxxxxxxxxxx:role/foo -s foo`

**Using an alias for a role configured in a file (~/.mortadelo/roles by default)**

`mortadelo assume -a bar`

**Configuring a new roles alias file (~/.mortadelo/roles by default):**

`mortadelo configure -a bar`-r arn:aws:iam::xxxxxxxxxxxx:role/bar`
 

**Roles file example**

```
[alias_for_foo]
arn = arn:aws:iam::xxxxxxxxxxxx:role/foo

[alias_for_bar]
arn = arn:aws:iam::yyyyyyyyyyyy:role/bar
```
