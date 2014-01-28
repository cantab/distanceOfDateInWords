# distanceOfDateInWords FileMaker Custom Function

FileMaker custom function to report the approximate distance in time between two dates as words.

## Introduction

distanceOfDateInWords is a FileMaker custom function to express a time interval in words, given two input dates.

## Syntax

distanceOfDateInWords(firstDate, secondDate)

## Dates in the Past

If the first date is more than 720 days before the second date, the custom function returns an approximate number of years in the form "over XXX years ago"

If the first date is between 720 days and 61 days before the second date, the custom function returns an approximate number of months in the form "about XXX months ago"

If the first date is 60 days or less before the second date, the custom function returns a number of days in the form "XXX days ago"

## Dates Nearby

If the first date is 1 day before the second date, the custom function returns "yesterday"

If the first date is the same as the second date, the custom function returns "today"

If the first date is 1 day after the second date, the custom function returns "tomorrow"

## Dates in the Future

If the first date is 60 days or less after the second date, the custom function returns a number of days in the form "XXX days time"

If the first date is between 61 days and 720 days after the second date, the custom function returns an approximate number of months in the form "about XXX months time"

If the first date is more than 720 days after the second date, the custom function returns an approximate number of years in the form "over XXX years time"

## Examples

	distanceOfDateInWords(Date (1, 20, 2012), Date (1, 20, 2014)) => over 2 years ago

	distanceOfDateInWords(Date (1, 20, 2013), Date (1, 20, 2014)) => about 12 months ago
	
	distanceOfDateInWords(Date (10, 20, 2013), Date (1, 20, 2014)) => about 3 months ago
	
	distanceOfDateInWords(Date (11, 20, 2013), Date (1, 20, 2014)) => about 2 months ago
	
	distanceOfDateInWords(Date (11, 21, 2013), Date (1, 20, 2014)) => 60 days ago
	
	distanceOfDateInWords(Date (1, 2, 2014), Date (1, 20, 2014)) => 18 days ago
	
	distanceOfDateInWords(Date (1, 18, 2014), Date (1, 20, 2014)) => 2 days ago
	
	distanceOfDateInWords(Date (1, 19, 2014), Date (1, 20, 2014)) => yesterday
	
	distanceOfDateInWords(Date (1, 20, 2014), Date (1, 20, 2014)) => today
	
	distanceOfDateInWords(Date (1, 21, 2014), Date (1, 20, 2014)) => tomorrow
	
	distanceOfDateInWords(Date (1, 22, 2014), Date (1, 20, 2014)) => 2 days time
	
	distanceOfDateInWords(Date (2, 7, 2014), Date (1, 20, 2014)) => 18 days time
	
	distanceOfDateInWords(Date (3, 21, 2014), Date (1, 20, 2014)) => 60 days time
	
	distanceOfDateInWords(Date (3, 22, 2014), Date (1, 20, 2014)) => about 2 months time
	
	distanceOfDateInWords(Date (4, 20, 2014), Date (1, 20, 2014)) => about 3 months time
	
	distanceOfDateInWords(Date (1, 20, 2015), Date (1, 20, 2014)) => about 12 months time
	
	distanceOfDateInWords(Date (1, 20, 2016), Date (1, 20, 2014)) => over 2 years time
	
## Credit

Inspired by and adapted from [10-patches] (https://github.com/edavis10/redmine/blob/master/config/initializers/10-patches.rb) to [Redmine] (https://github.com/edavis10/redmine)

## Contact

Comments and bug reports are welcome.

## Contributing

Feel free to drop us a line to let us know you would like to work on something or if you have an idea. Otherwise, fork, code, commit, push and create pull request, *viz*:

1. Create a fork of the repo from http://github.com/cantab/distanceOfDateInWords
2. Create your feature branch (`git checkout -b new-feature`).
2. Write some tests (if possible).
3. Write the code that allows the tests to pass.
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin new-feature`).
5. Create a new [Pull Request] (https://help.github.com/articles/using-pull-requests).

More details on how to contribute can be found at this great Thoughtbot blogpost [8 (new) steps for fixing other people's code] (http://robots.thoughtbot.com/8-new-steps-for-fixing-other-peoples-code).

## License

Copyright (c) 2013-2014 Chong-Yee Khoo. All rights reserved.

MIT License

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

