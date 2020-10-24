# TextTools4

TextTools4 is a library that gives you the all the details on your provided text.

Alpha Release v0.1.2

## Installing and Importing TextTools4

You can install TextTools4 through PyPi.

```sh
pip install TextTools4
```

Import TextTools4 as you would normally import a library.

```py
import TextTools4 as tt4
```

You can also import the classes individually.

```py
from TextTools4 import GetText, Chart, Tools
```

## Modules

## GetText

The GetText class contains functions to extract text from a PDF or a docx file and return a string representation of the text.

```py
tt4.GetText.get_pdf(filepath)
```
This function takes in a valid filepath to a PDF document and uses PyPDF4 to get the text. It then returns a string with all of the raw content on the page. (We are adding functionality to return a list of strings, with each item being the raw text of a single page).

```py
tt4.GetText.get_doc(filepath)
```
This function takes in a valid filepath to a doc or docx document and uses the docx library to get the text. It then returns a string with all of the raw content on the page.

## Chart

The Chart class creates a bar chart of the most popular words in a provided text.

```py
tt4.Chart.create(src = None, top = 10, other = False, text_title = None, common_words = 'default')
```

 - src: provide source text to create chart on
 - top: number of words you want displayed on the chart
 - other: adds 'other' to chart, showing the number of all the words not in the chart
 - text_title: title of chart, if not provided provides default title
 - common_words: words to exclude from the graph. There are three presets: 'default', 'none', and 'strict'.
 
Default: ["the", "be", "to", "of", "and", "a", "an", "in", "is", "you", "but", "for", "I"]
None: [ ]
Strict: ["the", "be", "to", "of", "and", "a", "an", "in", "is", "you", "but", "for", "I", "with", "it", "my", "me", "us"]

You can also provide a custom list with the words you choose to exclude.

## Tools

The Tools class contains tools to help you understand your text.

```py
tt4.Tools.reading_ease(text)
```

This function takes in a text and returns the Flesch Reading Ease Score. Reading ease is important because if your text has too low of a reading ease, you will not be able to reach as many people. The FRE is the most popular and widely accepted method to measure reading ease. 

More information on the [Flesch Reading Ease Score.](https://en.wikipedia.org/wiki/Flesch–Kincaid_readability_tests#Flesch_reading_ease)

```py
tt4.Tools.grade_level(text)
```

This function takes in a text and returns the Flesch-Kincaid Grade Level of the text. This number represents the number of years of schooling (from Grade 1) a person should have to understand this text. The Flesch-Kincaid Grade Level is the most popular method of  finding the grade level for a given text.

More information on the [Flesch-Kincaid Grade Level.](https://en.wikipedia.org/wiki/Flesch–Kincaid_readability_tests#Flesch–Kincaid_grade_level)

```py
tt4.Tools.split(text, length)
```

This function takes in a text and a length and splits the text into chunks of length, and returns a list of strings of equal (if there is no remainder) length.

```py
tt4.Tools.sarcastext(text)
```

This function takes in a text and returns a string with all of the characters in the text randomly made uppercase/lowercase to make the text sarcastic.

```py
tt4.Tools.table(data, sides=["|", "_"])
```

This function takes in two parameters, the data of type dict and a list sides. It returns a string table with two columns, with the vertical borders as sides[0] and the horizontal borders as sides[1].

## License

MIT

### Thank you for using TextTools4! - SR2020
