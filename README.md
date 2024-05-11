### Hexlet tests and linter status:
[![Actions Status](https://github.com/S1THOF/frontend-project-46/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/S1THOF/frontend-project-46/actions)
<a href="https://codeclimate.com/github/S1THOF/frontend-project-46/maintainability"><img src="https://api.codeclimate.com/v1/badges/ebff09b2dc0018c1fbbf/maintainability" /></a>

---

### Description:
The console utility developed as a JavaScript student project. The difference generator is a program for identifying variances between two data structures. Such tools are frequently used for test output and automated tracking of configuration file alterations.

**Key features of the utility:**
* Compatibility with different input formats such as YML and JSON
* Generation of reports in plain text, stylish, and JSON formats

---

### Dependencies:
**dependencies:**
* commander
* lodash
* js-yaml

---

### Setup:
```
git clone git@github.com:S1THOF/frontend-project-46.git
```
```
sudo apt install make
```
```
make install
```

---

### Usage:
1. Help:

        gendiff -h
        Usage: gendiff [options] <filepath1> <filepath2> 

        Compares two configuration files and shows a difference.

        Options:
          -V, --version        output the version number
          -f, --format [type]  output format (default: "stylish")
          -h, --help           display help for command

2. Stylish formatter (default option):

        gendiff path/to/file path/to/another/file

        {
            common: {
              + follow: false
                setting1: Value 1
              - setting2: 200
              - setting3: true
              + setting3: null
              + setting4: blah blah
              + setting5: {
                    key5: value5
                }
            }
        }


3. Plain formatter:

        gendiff -f plain path/to/file path/to/another/file

        Property 'common.follow' was added with value: false
        Property 'common.setting2' was removed
        Property 'common.setting3' was updated. From true to null
        Property 'common.setting4' was added with value: 'blah blah'
        Property 'common.setting5' was added with value: [complex value]


4. JSON formatter:

        gendiff -f json path/to/file path/to/another/file

        [
          {
            "name": "common",
            "type": "nested",
            "children": [
              {
                "name": "follow",
                "type": "added",
                "value": false
              },
              {
                "name": "setting1",
                "type": "unchanged",
                "value": "Value 1"
              },
              {
                "name": "setting2",
                "type": "deleted",
                "value": 200
              },
            ]
          }
        ]

---
### Demo:
Stylish formatter:

<a href="https://asciinema.org/a/ZEAlJgQOqj2eCgw8QdI2c50QV" target="_blank"><img src="https://asciinema.org/a/ZEAlJgQOqj2eCgw8QdI2c50QV.svg" /></a>

---
Plain formatter:

<a href="https://asciinema.org/a/2Ta5br9O3NR89jqGscgFzkZnW" target="_blank"><img src="https://asciinema.org/a/2Ta5br9O3NR89jqGscgFzkZnW.svg" /></a>

---
JSON formatter:

<a href="https://asciinema.org/a/PC3lGot9mdXlu2fVEHSXanZ59" target="_blank"><img src="https://asciinema.org/a/PC3lGot9mdXlu2fVEHSXanZ59.svg" /></a>
