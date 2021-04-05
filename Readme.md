# Text normalization

Yet another text normalization project for automatic speech recognition for Croatian language.

This code is quick-and-dirty and work-in-progress.

The general workflow is similar to Google Sparrowhawk, but its in pure Python:

1. text is tokenized by spaces
2. each token is split into subtokens containing equal char type (alpha,number,rest)
3. each subtoken is classified into one of basic classes
4. tokens are grouped into higher-level classes containing several subtokens (eg. time contains two numbers and a separator)
5. every final token is verbalized to its final form

## Token classes

- unknown - symbol of unknown type
- ignore - silent symbol (eg. punctuation)
- word - regular words
- number - numbers
- time - time string (number, separator, number)
- abbreviation - abbreviation from a list in `hrvatski.py` file
- symbol  - symbol that can be pronounced (eg. precent, degree, @)

# TODO

- inflection (currently everything in nominative)
- list of symbols
- certain symbol can be both silent and pronounceable (eg. minus)
- list of abbreviations
- certain abbreviations can also be regular words (e.g. single letters followed by period)
- numbers (currently limited to below million and integers only)