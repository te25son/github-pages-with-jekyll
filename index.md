# Welcome to my blog

I'm glad you are here. I plan to talk about what I've been learning!

Here's a recent bit of code I was working on...

```
def dictparse(csvfilename, keyfield, separator, quote, quotestrategy):
    """
    Parses a CSV file and returns a dictionary of
    dictionaries.
    """
    table = {}

    with open(csvfilename, 'rt', newline='') as csvfile:
        csvreader = csv.DictReader(
            csvfile,
            skipinitialspace=True,
            delimiter=separator,  # what char should separate the data in the file
            quotechar=quote,  # specifies what the quote character is in file
            quoting=quotestrategy
        )

        for row in csvreader:
            table[row[keyfield]] = row

    return table, csvreader.fieldnames
    # fieldnames returns a list of the field names in a file, so
    # we don't have to know them beforehand :)
```
