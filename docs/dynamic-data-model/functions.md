---
sidebar_position: 5
---

# Functions

This page provides details of all available functions.

## Functions by Type
### Data Access Functions
[firstStr](#firststr), [firstVal](#firstval), [lastStr](#laststr), [lastVal](#lastval), [submissionStr](#submissionstr), [submissionVal](#submissionval)
### Date Functions
[new Date](#date), [dateAdd](#dateadd), [dateFormat](#dateformat), [dateFormatDistance](#dateformatdistance), [dateSubtract](#datesubtract),  [differenceInDays](#differenceindays), [differenceInHours](#differenceinhours), [differenceInMinutes](#differenceinminutes), [now](#now)
### Math Functions 
[min](#min), [max](#max), [power](#power)

## Function Reference

## Date

The Date function constructs a date object from parts like year, month day, etc:

The Date function must be used with the new keyword (to maintain compatibility with JavaScript).

### Syntax
```
new Date(year, monthIndex)
new Date(year, monthIndex, day)
new Date(year, monthIndex, day, hours)
new Date(year, monthIndex, day, hours, minutes)
new Date(year, monthIndex, day, hours, minutes, seconds)
new Date(year, monthIndex, day, hours, minutes, seconds, milliseconds)
```


Given at least a year and month, this form of Date() returns a Date object whose component values (year, month, day, hour, minute, second, and millisecond) all come from the following parameters. Any missing fields are given the lowest possible value (1 for day and 0 for every other component). The parameter values are all evaluated against the local time zone, rather than UTC.

If any parameter overflows its defined bounds, it "carries over". For example, if a monthIndex greater than 11 is passed in, those months will cause the year to increment; if a minutes greater than 59 is passed in, hours will increment accordingly, etc. Therefore, new Date(1990, 12, 1) will return January 1st, 1991; new Date(2020, 5, 19, 25, 65) will return 2:05 A.M. June 20th, 2020.

Similarly, if any parameter underflows, it "borrows" from the higher positions. For example, new Date(2020, 5, 0) will return May 31st, 2020.

* **year**: Integer value representing the year. Values from 0 to 99 map to the years 1900 to 1999. All other values are the actual year. See the example.
* **monthIndex**: Integer value representing the month, beginning with 0 for January to 11 for December.
* **day**: Optional
Integer value representing the day of the month. The default is 1.
* **hours**: Optional
Integer value between 0 and 23 representing the hour of the day. Defaults to 0.
* **minutes**: Optional
Integer value representing the minute segment of a time. The default is 0 minutes past the hour.
* **seconds**: Optional
Integer value representing the second segment of a time. The default is 0 seconds past the minute.
* **milliseconds**: Optional
Integer value representing the millisecond segment of a time. The default is 0 milliseconds past the second.

### Examples

```
new Date(1999, 9)
// Fri Oct 01 1999 00:00:00 GMT-0400 (Eastern Daylight Time)

new Date(1999, 9, 9)
// Sat Oct 09 1999 00:00:00 GMT-0400 (Eastern Daylight Time)

new Date(1999, 9, 9, 9)
// Sat Oct 09 1999 09:00:00 GMT-0400 (Eastern Daylight Time)

new Date(1999, 9, 9, 9, 9)
// Sat Oct 09 1999 09:09:00 GMT-0400 (Eastern Daylight Time)

new Date(1999, 9, 9, 9, 9, 9)
// Sat Oct 09 1999 09:09:09 GMT-0400 (Eastern Daylight Time)

new Date(1999, 9, 9, 9, 9, 9, 9)
// Sat Oct 09 1999 09:09:09 GMT-0400 (Eastern Daylight Time)

```

## dateAdd

Add the specified years, months, weeks, days, hours, minutes and seconds to the given date.

### Syntax

```

dateAdd(date, duration)

```
**date** - Date the date to be changed

**duration** - the object with years, months, weeks, days, hours, minutes and seconds to be added. Positive decimals will be rounded using Math.floor, decimals less than zero will be rounded using Math.ceil.


* *years*	Amount of years to be added
* *months*	Amount of months to be added
* *weeks*	Amount of weeks to be added
* *days*	Amount of days to be added
* *hours*	Amount of hours to be added
* *minutes*	Amount of minutes to be added
* *seconds*	Amount of seconds to be added

All values default to 0


### Example

```
// Add the following duration to 1 September 2014, 10:19:50
dateAdd(new Date(2014, 8, 1, 10, 19, 50), {
  years: 2,
  months: 9,
  weeks: 1,
  days: 7,
  hours: 5,
  minutes: 9,
  seconds: 30,
})
//=> Thu Jun 15 2017 15:29:20
```

Sourced from [https://date-fns.org/v2.29.3/docs/add](https://date-fns.org/v2.29.3/docs/add)

## dateFormat

Return the formatted date string in the given format. The result may vary by locale.

:::caution

Please note that the format tokens differ from Moment.js and other libraries. See: https://github.com/date-fns/date-fns/blob/master/docs/unicodeTokens.md

:::

The characters wrapped between two single quotes characters (') are escaped. Two single quotes in a row, whether inside or outside a quoted sequence, represent a 'real' single quote. (see the last example)

Format of the string is based on Unicode Technical Standard #35: https://www.unicode.org/reports/tr35/tr35-dates.html#Date_Field_Symbol_Table with a few additions (see note 7 below the table).

<table><thead><tr><th>Unit</th><th>Pattern</th><th>Result examples</th><th>Notes</th></tr></thead><tbody><tr><td>Era</td><td>G..GGG</td><td>AD, BC</td><td></td></tr><tr><td></td><td>GGGG</td><td>Anno Domini, Before Christ</td><td>2</td></tr><tr><td></td><td>GGGGG</td><td>A, B</td><td></td></tr><tr><td>Calendar year</td><td>y</td><td>44, 1, 1900, 2017</td><td>5</td></tr><tr><td></td><td>yo</td><td>44th, 1st, 0th, 17th</td><td>5,7</td></tr><tr><td></td><td>yy</td><td>44, 01, 00, 17</td><td>5</td></tr><tr><td></td><td>yyy</td><td>044, 001, 1900, 2017</td><td>5</td></tr><tr><td></td><td>yyyy</td><td>0044, 0001, 1900, 2017</td><td>5</td></tr><tr><td></td><td>yyyyy</td><td>...</td><td>3,5</td></tr><tr><td>Local week-numbering year</td><td>Y</td><td>44, 1, 1900, 2017</td><td>5</td></tr><tr><td></td><td>Yo</td><td>44th, 1st, 1900th, 2017th</td><td>5,7</td></tr><tr><td></td><td>YY</td><td>44, 01, 00, 17</td><td>5,8</td></tr><tr><td></td><td>YYY</td><td>044, 001, 1900, 2017</td><td>5</td></tr><tr><td></td><td>YYYY</td><td>0044, 0001, 1900, 2017</td><td>5,8</td></tr><tr><td></td><td>YYYYY</td><td>...</td><td>3,5</td></tr><tr><td>ISO week-numbering year</td><td>R</td><td>-43, 0, 1, 1900, 2017</td><td>5,7</td></tr><tr><td></td><td>RR</td><td>-43, 00, 01, 1900, 2017</td><td>5,7</td></tr><tr><td></td><td>RRR</td><td>-043, 000, 001, 1900, 2017</td><td>5,7</td></tr><tr><td></td><td>RRRR</td><td>-0043, 0000, 0001, 1900, 2017</td><td>5,7</td></tr><tr><td></td><td>RRRRR</td><td>...</td><td>3,5,7</td></tr><tr><td>Extended year</td><td>u</td><td>-43, 0, 1, 1900, 2017</td><td>5</td></tr><tr><td></td><td>uu</td><td>-43, 01, 1900, 2017</td><td>5</td></tr><tr><td></td><td>uuu</td><td>-043, 001, 1900, 2017</td><td>5</td></tr><tr><td></td><td>uuuu</td><td>-0043, 0001, 1900, 2017</td><td>5</td></tr><tr><td></td><td>uuuuu</td><td>...</td><td>3,5</td></tr><tr><td>Quarter (formatting)</td><td>Q</td><td>1, 2, 3, 4</td><td></td></tr><tr><td></td><td>Qo</td><td>1st, 2nd, 3rd, 4th</td><td>7</td></tr><tr><td></td><td>QQ</td><td>01, 02, 03, 04</td><td></td></tr><tr><td></td><td>QQQ</td><td>Q1, Q2, Q3, Q4</td><td></td></tr><tr><td></td><td>QQQQ</td><td>1st quarter, 2nd quarter, ...</td><td>2</td></tr><tr><td></td><td>QQQQQ</td><td>1, 2, 3, 4</td><td>4</td></tr><tr><td>Quarter (stand-alone)</td><td>q</td><td>1, 2, 3, 4</td><td></td></tr><tr><td></td><td>qo</td><td>1st, 2nd, 3rd, 4th</td><td>7</td></tr><tr><td></td><td>qq</td><td>01, 02, 03, 04</td><td></td></tr><tr><td></td><td>qqq</td><td>Q1, Q2, Q3, Q4</td><td></td></tr><tr><td></td><td>qqqq</td><td>1st quarter, 2nd quarter, ...</td><td>2</td></tr><tr><td></td><td>qqqqq</td><td>1, 2, 3, 4</td><td>4</td></tr><tr><td>Month (formatting)</td><td>M</td><td>1, 2, ..., 12</td><td></td></tr><tr><td></td><td>Mo</td><td>1st, 2nd, ..., 12th</td><td>7</td></tr><tr><td></td><td>MM</td><td>01, 02, ..., 12</td><td></td></tr><tr><td></td><td>MMM</td><td>Jan, Feb, ..., Dec</td><td></td></tr><tr><td></td><td>MMMM</td><td>January, February, ..., December</td><td>2</td></tr><tr><td></td><td>MMMMM</td><td>J, F, ..., D</td><td></td></tr><tr><td>Month (stand-alone)</td><td>L</td><td>1, 2, ..., 12</td><td></td></tr><tr><td></td><td>Lo</td><td>1st, 2nd, ..., 12th</td><td>7</td></tr><tr><td></td><td>LL</td><td>01, 02, ..., 12</td><td></td></tr><tr><td></td><td>LLL</td><td>Jan, Feb, ..., Dec</td><td></td></tr><tr><td></td><td>LLLL</td><td>January, February, ..., December</td><td>2</td></tr><tr><td></td><td>LLLLL</td><td>J, F, ..., D</td><td></td></tr><tr><td>Local week of year</td><td>w</td><td>1, 2, ..., 53</td><td></td></tr><tr><td></td><td>wo</td><td>1st, 2nd, ..., 53th</td><td>7</td></tr><tr><td></td><td>ww</td><td>01, 02, ..., 53</td><td></td></tr><tr><td>ISO week of year</td><td>I</td><td>1, 2, ..., 53</td><td>7</td></tr><tr><td></td><td>Io</td><td>1st, 2nd, ..., 53th</td><td>7</td></tr><tr><td></td><td>II</td><td>01, 02, ..., 53</td><td>7</td></tr><tr><td>Day of month</td><td>d</td><td>1, 2, ..., 31</td><td></td></tr><tr><td></td><td>do</td><td>1st, 2nd, ..., 31st</td><td>7</td></tr><tr><td></td><td>dd</td><td>01, 02, ..., 31</td><td></td></tr><tr><td>Day of year</td><td>D</td><td>1, 2, ..., 365, 366</td><td>9</td></tr><tr><td></td><td>Do</td><td>1st, 2nd, ..., 365th, 366th</td><td>7</td></tr><tr><td></td><td>DD</td><td>01, 02, ..., 365, 366</td><td>9</td></tr><tr><td></td><td>DDD</td><td>001, 002, ..., 365, 366</td><td></td></tr><tr><td></td><td>DDDD</td><td>...</td><td>3</td></tr><tr><td>Day of week (formatting)</td><td>E..EEE</td><td>Mon, Tue, Wed, ..., Sun</td><td></td></tr><tr><td></td><td>EEEE</td><td>Monday, Tuesday, ..., Sunday</td><td>2</td></tr><tr><td></td><td>EEEEE</td><td>M, T, W, T, F, S, S</td><td></td></tr><tr><td></td><td>EEEEEE</td><td>Mo, Tu, We, Th, Fr, Sa, Su</td><td></td></tr><tr><td>ISO day of week (formatting)</td><td>i</td><td>1, 2, 3, ..., 7</td><td>7</td></tr><tr><td></td><td>io</td><td>1st, 2nd, ..., 7th</td><td>7</td></tr><tr><td></td><td>ii</td><td>01, 02, ..., 07</td><td>7</td></tr><tr><td></td><td>iii</td><td>Mon, Tue, Wed, ..., Sun</td><td>7</td></tr><tr><td></td><td>iiii</td><td>Monday, Tuesday, ..., Sunday</td><td>2,7</td></tr><tr><td></td><td>iiiii</td><td>M, T, W, T, F, S, S</td><td>7</td></tr><tr><td></td><td>iiiiii</td><td>Mo, Tu, We, Th, Fr, Sa, Su</td><td>7</td></tr><tr><td>Local day of week (formatting)</td><td>e</td><td>2, 3, 4, ..., 1</td><td></td></tr><tr><td></td><td>eo</td><td>2nd, 3rd, ..., 1st</td><td>7</td></tr><tr><td></td><td>ee</td><td>02, 03, ..., 01</td><td></td></tr><tr><td></td><td>eee</td><td>Mon, Tue, Wed, ..., Sun</td><td></td></tr><tr><td></td><td>eeee</td><td>Monday, Tuesday, ..., Sunday</td><td>2</td></tr><tr><td></td><td>eeeee</td><td>M, T, W, T, F, S, S</td><td></td></tr><tr><td></td><td>eeeeee</td><td>Mo, Tu, We, Th, Fr, Sa, Su</td><td></td></tr><tr><td>Local day of week (stand-alone)</td><td>c</td><td>2, 3, 4, ..., 1</td><td></td></tr><tr><td></td><td>co</td><td>2nd, 3rd, ..., 1st</td><td>7</td></tr><tr><td></td><td>cc</td><td>02, 03, ..., 01</td><td></td></tr><tr><td></td><td>ccc</td><td>Mon, Tue, Wed, ..., Sun</td><td></td></tr><tr><td></td><td>cccc</td><td>Monday, Tuesday, ..., Sunday</td><td>2</td></tr><tr><td></td><td>ccccc</td><td>M, T, W, T, F, S, S</td><td></td></tr><tr><td></td><td>cccccc</td><td>Mo, Tu, We, Th, Fr, Sa, Su</td><td></td></tr><tr><td>AM, PM</td><td>a..aa</td><td>AM, PM</td><td></td></tr><tr><td></td><td>aaa</td><td>am, pm</td><td></td></tr><tr><td></td><td>aaaa</td><td>a.m., p.m.</td><td>2</td></tr><tr><td></td><td>aaaaa</td><td>a, p</td><td></td></tr><tr><td>AM, PM, noon, midnight</td><td>b..bb</td><td>AM, PM, noon, midnight</td><td></td></tr><tr><td></td><td>bbb</td><td>am, pm, noon, midnight</td><td></td></tr><tr><td></td><td>bbbb</td><td>a.m., p.m., noon, midnight</td><td>2</td></tr><tr><td></td><td>bbbbb</td><td>a, p, n, mi</td><td></td></tr><tr><td>Flexible day period</td><td>B..BBB</td><td>at night, in the morning, ...</td><td></td></tr><tr><td></td><td>BBBB</td><td>at night, in the morning, ...</td><td>2</td></tr><tr><td></td><td>BBBBB</td><td>at night, in the morning, ...</td><td></td></tr><tr><td>Hour [1-12]</td><td>h</td><td>1, 2, ..., 11, 12</td><td></td></tr><tr><td></td><td>ho</td><td>1st, 2nd, ..., 11th, 12th</td><td>7</td></tr><tr><td></td><td>hh</td><td>01, 02, ..., 11, 12</td><td></td></tr><tr><td>Hour [0-23]</td><td>H</td><td>0, 1, 2, ..., 23</td><td></td></tr><tr><td></td><td>Ho</td><td>0th, 1st, 2nd, ..., 23rd</td><td>7</td></tr><tr><td></td><td>HH</td><td>00, 01, 02, ..., 23</td><td></td></tr><tr><td>Hour [0-11]</td><td>K</td><td>1, 2, ..., 11, 0</td><td></td></tr><tr><td></td><td>Ko</td><td>1st, 2nd, ..., 11th, 0th</td><td>7</td></tr><tr><td></td><td>KK</td><td>01, 02, ..., 11, 00</td><td></td></tr><tr><td>Hour [1-24]</td><td>k</td><td>24, 1, 2, ..., 23</td><td></td></tr><tr><td></td><td>ko</td><td>24th, 1st, 2nd, ..., 23rd</td><td>7</td></tr><tr><td></td><td>kk</td><td>24, 01, 02, ..., 23</td><td></td></tr><tr><td>Minute</td><td>m</td><td>0, 1, ..., 59</td><td></td></tr><tr><td></td><td>mo</td><td>0th, 1st, ..., 59th</td><td>7</td></tr><tr><td></td><td>mm</td><td>00, 01, ..., 59</td><td></td></tr><tr><td>Second</td><td>s</td><td>0, 1, ..., 59</td><td></td></tr><tr><td></td><td>so</td><td>0th, 1st, ..., 59th</td><td>7</td></tr><tr><td></td><td>ss</td><td>00, 01, ..., 59</td><td></td></tr><tr><td>Fraction of second</td><td>S</td><td>0, 1, ..., 9</td><td></td></tr><tr><td></td><td>SS</td><td>00, 01, ..., 99</td><td></td></tr><tr><td></td><td>SSS</td><td>000, 001, ..., 999</td><td></td></tr><tr><td></td><td>SSSS</td><td>...</td><td>3</td></tr><tr><td>Timezone (ISO-8601 w/ Z)</td><td>X</td><td>-08, +0530, Z</td><td></td></tr><tr><td></td><td>XX</td><td>-0800, +0530, Z</td><td></td></tr><tr><td></td><td>XXX</td><td>-08:00, +05:30, Z</td><td></td></tr><tr><td></td><td>XXXX</td><td>-0800, +0530, Z, +123456</td><td>2</td></tr><tr><td></td><td>XXXXX</td><td>-08:00, +05:30, Z, +12:34:56</td><td></td></tr><tr><td>Timezone (ISO-8601 w/o Z)</td><td>x</td><td>-08, +0530, +00</td><td></td></tr><tr><td></td><td>xx</td><td>-0800, +0530, +0000</td><td></td></tr><tr><td></td><td>xxx</td><td>-08:00, +05:30, +00:00</td><td>2</td></tr><tr><td></td><td>xxxx</td><td>-0800, +0530, +0000, +123456</td><td></td></tr><tr><td></td><td>xxxxx</td><td>-08:00, +05:30, +00:00, +12:34:56</td><td></td></tr><tr><td>Timezone (GMT)</td><td>O...OOO</td><td>GMT-8, GMT+5:30, GMT+0</td><td></td></tr><tr><td></td><td>OOOO</td><td>GMT-08:00, GMT+05:30, GMT+00:00</td><td>2</td></tr><tr><td>Timezone (specific non-locat.)</td><td>z...zzz</td><td>GMT-8, GMT+5:30, GMT+0</td><td>6</td></tr><tr><td></td><td>zzzz</td><td>GMT-08:00, GMT+05:30, GMT+00:00</td><td>2,6</td></tr><tr><td>Seconds timestamp</td><td>t</td><td>512969520</td><td>7</td></tr><tr><td></td><td>tt</td><td>...</td><td>3,7</td></tr><tr><td>Milliseconds timestamp</td><td>T</td><td>512969520900</td><td>7</td></tr><tr><td></td><td>TT</td><td>...</td><td>3,7</td></tr><tr><td>Long localized date</td><td>P</td><td>04/29/1453</td><td>7</td></tr><tr><td></td><td>PP</td><td>Apr 29, 1453</td><td>7</td></tr><tr><td></td><td>PPP</td><td>April 29th, 1453</td><td>7</td></tr><tr><td></td><td>PPPP</td><td>Friday, April 29th, 1453</td><td>2,7</td></tr><tr><td>Long localized time</td><td>p</td><td>12:00 AM</td><td>7</td></tr><tr><td></td><td>pp</td><td>12:00:00 AM</td><td>7</td></tr><tr><td></td><td>ppp</td><td>12:00:00 AM GMT+2</td><td>7</td></tr><tr><td></td><td>pppp</td><td>12:00:00 AM GMT+02:00</td><td>2,7</td></tr><tr><td>Combination of date and time</td><td>Pp</td><td>04/29/1453, 12:00 AM</td><td>7</td></tr><tr><td></td><td>PPpp</td><td>Apr 29, 1453, 12:00:00 AM</td><td>7</td></tr><tr><td></td><td>PPPppp</td><td>April 29th, 1453 at ...</td><td>7</td></tr><tr><td></td><td>PPPPpppp</td><td>Friday, April 29th, 1453 at ...</td><td>2,7</td></tr></tbody></table>

Notes:

1. "Formatting" units (e.g. formatting quarter) in the default en-US locale are the same as "stand-alone" units, but are different in some languages. "Formatting" units are declined according to the rules of the language in the context of a date. "Stand-alone" units are always nominative singular:
```
format(new Date(2017, 10, 6), 'do LLLL', {locale: cs}) //=> '6. listopad'

format(new Date(2017, 10, 6), 'do MMMM', {locale: cs}) //=> '6. listopadu'
```
2. Any sequence of the identical letters is a pattern, unless it is escaped by the single quote characters (see below). If the sequence is longer than listed in table (e.g. EEEEEEEEEEE) the output will be the same as default pattern for this unit, usually the longest one (in case of ISO weekdays, EEEE). Default patterns for units are marked with "2" in the last column of the table.
```
format(new Date(2017, 10, 6), 'MMM') //=> 'Nov'

format(new Date(2017, 10, 6), 'MMMM') //=> 'November'

format(new Date(2017, 10, 6), 'MMMMM') //=> 'N'

format(new Date(2017, 10, 6), 'MMMMMM') //=> 'November'

format(new Date(2017, 10, 6), 'MMMMMMM') //=> 'November'
```
3. Some patterns could be unlimited length (such as yyyyyyyy). The output will be padded with zeros to match the length of the pattern.
```
format(new Date(2017, 10, 6), 'yyyyyyyy') //=> '00002017'
```
4. QQQQQ and qqqqq could be not strictly numerical in some locales. These tokens represent the shortest form of the quarter.

5. The main difference between y and u patterns are B.C. years:

<table><thead><tr><th>Year</th><th><code>y</code></th><th><code>u</code></th></tr></thead><tbody><tr><td>AC 1</td><td>1</td><td>1</td></tr><tr><td>BC 1</td><td>1</td><td>0</td></tr><tr><td>BC 2</td><td>2</td><td>-1</td></tr></tbody></table>

Also yy always returns the last two digits of a year, while uu pads single digit years to 2 characters and returns other years unchanged:

<table><thead><tr><th>Year</th><th><code>yy</code></th><th><code>uu</code></th></tr></thead><tbody><tr><td>1</td><td>01</td><td>01</td></tr><tr><td>14</td><td>14</td><td>14</td></tr><tr><td>376</td><td>76</td><td>376</td></tr><tr><td>1453</td><td>53</td><td>1453</td></tr></tbody></table>

The same difference is true for local and ISO week-numbering years (Y and R), except local week-numbering years are dependent on options.weekStartsOn and options.firstWeekContainsDate (compare getISOWeekYear and getWeekYear).

6. Specific non-location timezones are currently unavailable in date-fns, so right now these tokens fall back to GMT timezones.

7. These patterns are not in the Unicode Technical Standard #35:

* i: ISO day of week
* I: ISO week of year
* R: ISO week-numbering year
* t: seconds timestamp
* T: milliseconds timestamp
* o: ordinal number modifier
* P: long localized date
* p: long localized time

8. YY and YYYY tokens represent week-numbering years but they are often confused with years. You should enable options.useAdditionalWeekYearTokens to use them. See: https://github.com/date-fns/date-fns/blob/master/docs/unicodeTokens.md

9. D and DD tokens represent days of the year but they are often confused with days of the month. You should enable options.useAdditionalDayOfYearTokens to use them. See: https://github.com/date-fns/date-fns/blob/master/docs/unicodeTokens.md

### Syntax

```
formatDate(date, format)
```

* *date* - Date the original date
* *format* - the string of tokens

### Example

```
// Represent 11 February 2014 in middle-endian format:
const result = formatDate(new Date(2014, 1, 11), 'MM/dd/yyyy')
//=> '02/11/2014'
```

Sourced from [https://date-fns.org/v2.29.3/docs/format](https://date-fns.org/v2.29.3/docs/format)


## dateFormatDistance

Return the distance between the given dates in words.

<table><thead><tr><th>Distance between dates</th><th>Result</th></tr></thead><tbody><tr><td>0 ... 30 secs</td><td>less than a minute</td></tr><tr><td>30 secs ... 1 min 30 secs</td><td>1 minute</td></tr><tr><td>1 min 30 secs ... 44 mins 30 secs</td><td>[2..44] minutes</td></tr><tr><td>44 mins ... 30 secs ... 89 mins 30 secs</td><td>about 1 hour</td></tr><tr><td>89 mins 30 secs ... 23 hrs 59 mins 30 secs</td><td>about [2..24] hours</td></tr><tr><td>23 hrs 59 mins 30 secs ... 41 hrs 59 mins 30 secs</td><td>1 day</td></tr><tr><td>41 hrs 59 mins 30 secs ... 29 days 23 hrs 59 mins 30 secs</td><td>[2..30] days</td></tr><tr><td>29 days 23 hrs 59 mins 30 secs ... 44 days 23 hrs 59 mins 30 secs</td><td>about 1 month</td></tr><tr><td>44 days 23 hrs 59 mins 30 secs ... 59 days 23 hrs 59 mins 30 secs</td><td>about 2 months</td></tr><tr><td>59 days 23 hrs 59 mins 30 secs ... 1 yr</td><td>[2..12] months</td></tr><tr><td>1 yr ... 1 yr 3 months</td><td>about 1 year</td></tr><tr><td>1 yr 3 months ... 1 yr 9 month s</td><td>over 1 year</td></tr><tr><td>1 yr 9 months ... 2 yrs</td><td>almost 2 years</td></tr><tr><td>N yrs ... N yrs 3 months</td><td>about N years</td></tr><tr><td>N yrs 3 months ... N yrs 9 months</td><td>over N years</td></tr><tr><td>N yrs 9 months ... N+1 yrs</td><td>almost N+1 years</td></tr></tbody></table>

### Syntax
```
formatDistance(date, baseDate, [options])
```

* *date* - Date, the date
* *baseDate* - Date, the date to compare with
* *options* - (optional) missing or {addSuffix: true} to indicate to add "ago" or {includeSeconds: true} to include seconds (or can be combined like {addSuffix: true, includeSeconds: true} )

### Example

```
// What is the distance between 2 July 2014 and 1 January 2015?
dateFormatDistance(new Date(2014, 6, 2), new Date(2015, 0, 1))
//=> '6 months'


// What is the distance between 1 January 2015 00:00:15
// and 1 January 2015 00:00:00, including seconds?
dateFormatDistance(
  new Date(2015, 0, 1, 0, 0, 15),
  new Date(2015, 0, 1, 0, 0, 0),
  { includeSeconds: true }
)
//=> 'less than 20 seconds'

// What is the distance from 1 January 2016
// to 1 January 2015, with a suffix?
dateFormatDistance(new Date(2015, 0, 1), new Date(2016, 0, 1), {
  addSuffix: true
})
//=> 'about 1 year ago'


```

Sourced from [https://date-fns.org/v2.29.3/docs/formatDistance](https://date-fns.org/v2.29.3/docs/formatDistance)
## dateSubtract

Subtract the specified years, months, weeks, days, hours, minutes and seconds from the given date.

### Syntax
```
dateSubtract(date, duration)
```

* *date* - Date, the date to be changed
* *duration*	- the object with years, months, weeks, days, hours, minutes and seconds to be subtracted

<table><thead><tr><th>Key</th><th>Description</th></tr></thead><tbody><tr><td>years</td><td>Amount of years to be subtracted</td></tr><tr><td>months</td><td>Amount of months to be subtracted</td></tr><tr><td>weeks</td><td>Amount of weeks to be subtracted</td></tr><tr><td>days</td><td>Amount of days to be subtracted</td></tr><tr><td>hours</td><td>Amount of hours to be subtracted</td></tr><tr><td>minutes</td><td>Amount of minutes to be subtracted</td></tr><tr><td>seconds</td><td>Amount of seconds to be subtracted</td></tr></tbody></table>

### Example
```
// Subtract the following duration from 15 June 2017 15:29:20
dateSubtract(new Date(2017, 5, 15, 15, 29, 20), {
  years: 2,
  months: 9,
  weeks: 1,
  days: 7,
  hours: 5,
  minutes: 9,
  seconds: 30
})
//=> Mon Sep 1 2014 10:19:50

```

Sourced from [https://date-fns.org/v2.29.3/docs/formatDistance](https://date-fns.org/v2.29.3/docs/formatDistance)

## differenceInDays

Get the number of full day periods between two dates. Fractional days are truncated towards zero.

One "full day" is the distance between a local time in one day to the same local time on the next or previous day. A full day can sometimes be less than or more than 24 hours if a daylight savings change happens between two dates.

### Syntax

```
differenceInDays(dateLeft, dateRight)
```

* *dateLeft* - Date, the later date
* *dateRight* - Date, the earlier date

### Examples

```
// How many full days are between
// 2 July 2011 23:00:00 and 2 July 2012 00:00:00?
differenceInDays(
  new Date(2012, 6, 2, 0, 0),
  new Date(2011, 6, 2, 23, 0)
)
//=> 365

// How many full days are between
// 2 July 2011 23:59:00 and 3 July 2011 00:01:00?
differenceInDays(
  new Date(2011, 6, 3, 0, 1),
  new Date(2011, 6, 2, 23, 59)
)
//=> 0

// How many full days are between
// 1 March 2020 0:00 and 1 June 2020 0:00 ?
// Note: because local time is used, the
// result will always be 92 days, even in
// time zones where DST starts and the
// period has only 92*24-1 hours.
const result = differenceInDays(
  new Date(2020, 5, 1),
  new Date(2020, 2, 1)
)
//=> 92

```

Sourced from https://date-fns.org/v2.29.3/docs/differenceInDays

## differenceInHours

Get the number of hours between the given dates

### Syntax

```

differenceInHours(dateLeft, dateRight)

```

* *dateLeft*	- Date, the later date
* *dateRight*	- Date, the earlier date

### Example

```

// How many hours are between 2 July 2014 06:50:00 and 2 July 2014 19:00:00?
differenceInHours(
  new Date(2014, 6, 2, 19, 0),
  new Date(2014, 6, 2, 6, 50)
)
//=> 12
```

Sourced from https://date-fns.org/v2.29.3/docs/differenceInHours

## differenceInMinutes

Get the signed number of full (rounded towards 0) minutes between the given dates

### Syntax

```
differenceInMinutes(dateLeft, dateRight)

```

* *dateLeft* - Date, the later date
* *dateRight* - Date, the earlier date

### Example

```
// How many minutes are between 2 July 2014 12:07:59 and 2 July 2014 12:20:00?
differenceInMinutes(
  new Date(2014, 6, 2, 12, 20, 0),
  new Date(2014, 6, 2, 12, 7, 59)
)
//=> 12

// How many minutes are between 10:01:59 and 10:00:00
differenceInMinutes(
  new Date(2000, 0, 1, 10, 0, 0),
  new Date(2000, 0, 1, 10, 1, 59)
)
//=> -1

```
## max

Determine the maximum of a list of numbers.

### Syntax

```
max(number1, number2, number3, ...)
```

### Example
```
max(1,2,3)
// => 3
```

## min
Determine the minimum of a list of numbers.

### Syntax

```
min(number1, number2, number3, ...)
```

### Example
```
min(1,2,3)
// => 1
```

## now

Returns the current date.  It is sensitive to the [Simulator](/creating-plans/simulator)'s *as at* feature so sometimes it will return the simulated date, not the actual date.

### Syntax

```
now()
```

### Example

```
now()
// => current date time
```

## firstStr
## firstVal

firstVal and firstStr retrieve the first submitted value of the specific [data reference](./referencing-data).

Note for the plan entity, there is no difference between firstVal and lastVal since there is only one instance of a plan.

If the form was never submitted it returns [undefined](./operators)

### Str vs Val versions

The difference between the *Str and *Val variations is the data type that is returned.  If *Str* is used, the value is ready to be displayed to a user and the system will attempt to format it with whatever metadata can be found.  In the future, this will pick up units labels and decimals defined by a Unit of Measure. So use *Str* versions when you want to display the value in a [view](/creating-plans/presentation/views).

The *Val* version should be used if you wanted to interrogate the value.  For example if you wanted to use *min*, *max*, *&gt;* against the results.

### Syntax
```
firstStr("data reference")
firstVal("data reference")
```
### Examples

```
firstStr("submission.form1.field1")
// Returns a printable string of field1 in form1 the first time it was submitted

firstVal("submission.form1.field1")
// Returns the value of field1 in form1 the first time it was submitted

firstStr("plan.status")
// Returns the plan status
```

## lastStr
## lastVal

lastVal and lastStr retrieve the latest submitted value of the specific [data reference](./referencing-data).

Note for the plan entity, there is no difference between firstVal and lastVal since there is only one instance of a plan.

If the form was never submitted it returns [undefined](./operators)

See [Str vs Val versions](#str-vs-val-versions)

### Syntax
```
lastStr("data reference")
lastVal("data reference")
```
### Examples

```
lastStr("submission.form1.field1")
// Returns a printable string of field1 in form1 the last time it was submitted

lastVal("submission.form1.field1")
// Returns the value of field1 in form1 the last time it was submitted

lastStr("plan.status")
// Returns the plan status
```
## submissionStr
## submissionVal

submissionVal and submissionStr retrieve the submitted value of the specific [data reference](./referencing-data) for the form submission that is in [context](/dynamic-data-model/healix-calculation-grammar#calculation-contexts).

See [Str vs Val versions](#str-vs-val-versions)

Unlike lastVal, etc., use only the field name.  "submission.form-name" is implied.  You may not access plan attributes.

### Syntax
```
submissionStr("field name")
submissionVal("field name")
```
### Examples

```
submissionStr("field1")
// Returns a printable string of field1 in the form that was submitted

submissionVal("field1")
// Returns the value of field1 in the form that was submitted

```
## power

The power function computes an exponential.

### Syntax

```
power(base,exp)
```

### Example

```
power(2,2)
// => 4
```