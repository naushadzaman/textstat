textstat
========

Python package to calculate statistics from text to determine readability, complexity and grade level of a particular corpus.


Install
-------

You can install textstat either via the Python Package Index (PyPI) or from source.

To install using pip:

```shell
$ pip install textstat
```

To install using easy_install:

```shell
$ easy_install textstat
```

Downloading and installing from source

Download the latest version of textstat from http://pypi.python.org/pypi/textstat/

You can install it by doing the following,:

```shell
$ tar xfz textstat-*.tar.gz

$ cd textstat-*/

$ python setup.py build

$ python setup.py install # as root
```

List of Functions
----

### Syllable Count

function name - syllable_count(text)

Returns the number of syllables present in the given text.

### Lexicon Count

function name - lexicon_count(text, TRUE/FALSE)

Calculates the number of words present in the text.
TRUE/FALSE specifies whether we need to take
punctuation symbols into account while counting lexicons.
Default value is TRUE, which removes the punctuation before counting
lexicon items.

### Sentence Count

function name - sentence_count(text)

Returns the number of sentences present in the given text.


### The Flesch Reading Ease formula

function name - flesch_reading_ease(text)

Returns the Flesch Reading Ease Score.

The following table can be helpful to assess the ease of readability in a document.
However, the table is an example of values.
While the maximum score is 121.22, there is no limit on how low the score can be.
A negative score is valid.

* 90-100 : Very Easy
* 80-89 : Easy
* 70-79 : Fairly Easy
* 60-69 : Standard
* 50-59 : Fairly Difficult
* 30-49 : Difficult
* 0-29 : Very Confusing

Further reading: https://en.wikipedia.org/wiki/Flesch%E2%80%93Kincaid_readability_tests#Flesch_reading_ease

### The The Flesch-Kincaid Grade Level

function name - flesch_kincaid_grade(text)

Returns the grade score using the Flesch-Kincaid Grade Formula.

For example, a score of 9.3 means that a ninth grader would be able to
read the document.

## The Fog Scale (Gunning FOG Formula)

function name - gunning_fog(text)

Returns the FOG index of the given text.

### The SMOG Index

function name - smog_index(text)

Returns the SMOG index of the given text.

### Automated Readability Index

function name - automated_readability_index(text)

Returns the ARI (Automated Readability Index)
which outputs a number that approximates the
grade level needed to comprehend the text.

For example if the ARI is 6.5, then the grade level to comprehend the text is
6th to 7th grade.

### The Coleman-Liau Index

function name - coleman_liau_index(text)

Returns the grade level of the text using the Coleman-Liau Formula.

### Linsear Write Formula

function name - linsear_write_formula(text)

Returns the grade level using the Linsear Write Formula.

### Dale-Chall Readability Score

function name - dale_chall_readability_score(text)

Different from other tests,
since it uses a lookup table of the most commonly used 3000 English words.
Thus it returns the grade level using the New Dale-Chall Formula.

### Readability Consensus based upon all the above tests

function name - text_standard(text)

Based upon all the above tests,
returns the estimated school grade level required to understand the text.


Usage
----------
```python
import textstat

if __name__ == '__main__':
    test_data = "Playing games has always been thought to be important to" \
        " the development of well-balanced and creative children; however, what part," \
        " if any, they should play in the lives of adults has never been researched" \
        " that deeply." \
        " I believe that playing games is every bit as important for adults" \
        " as for children."
        " Not only is taking time out to play games with our children and other adults" \
        " valuable to building interpersonal relationships but is also a wonderful way" \
        " to release built up tension."

    print textstat.flesch_reading_ease(test_data)
    print textstat.smog_index(test_data)
    print textstat.flesch_kincaid_grade(test_data)
    print textstat.coleman_liau_index(test_data)
    print textstat.automated_readability_index(test_data)
    print textstat.dale_chall_readability_score(test_data)
    print textstat.difficult_words(test_data)
    print textstat.linsear_write_formula(test_data)
    print textstat.gunning_fog(test_data)
    print textstat.text_standard(test_data)
```

The argument (text) for all the defined functions remains the same -
i.e the text for which statistics need to be calculated.
