# Your calendarical fallacy is thinking...

## Days are 86,400 seconds long.

False. Even if you live in a place that doesn't have [Daylight Saving Time](https://en.wikipedia.org/wiki/Daylight_saving_time), you are still subject to rogue [leap seconds](https://en.wikipedia.org/wiki/Leap_second) that get inserted into our calendars every now and then. If you care about being precise, you care about leap seconds.

## Days are 24 hours long.

False. Many places around the world observe Daylight Saving Time, which means that people living in these locations will sometimes experience 23 hour days (when they "leap forward") and 25 hour days (when they "leap back").

## An hour will never occur twice in a single day
## Every day has a midnight
## Days start at midnight (or as close to it as possible)
## Everyone uses the Gregorian calendar
## Months always have 30 or 31 days in them
## OK... Months always have at least 28 days in them
## Month lengths follow regular cycles
## The current year is {2017}
## All the important years are four digits longs
## In a range of days, a day will not be missing in the middle of it
## In a range of months, a month will not be missing in the middle of it
## A year is twelve months
## A year is 365 (or 366) days
## Leap years occur every four years
## Leap years occur every four years except when the year is evenly divisible by 100
## The current year only changes at "New Years"

## Timezones always are on the hour mark
## OK... Timezones are always on the *half* hour mark
## *Fine*... Timezones are always on the *quarter* hour mark
## No location will ever change what time zone it's in

## This is all really complicated.

True!

## I never want to write code that handles all of this.

True! You should always use the Date and Time Services provided by the [ICU Project](http://userguide.icu-project.org/datetime). If you're an iOS/macOS developer, then you should always stick to `NSCalendar` and its cohorts.

