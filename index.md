# Your calendrical fallacy is thinking...

## <a name="Days_are_86400_seconds_long"></a>Days are 86,400 seconds long

False. Even if you live in a place that doesn't have [Daylight Saving Time](https://en.wikipedia.org/wiki/Daylight_saving_time), you are still subject to rogue [leap seconds](https://en.wikipedia.org/wiki/Leap_second) that get inserted into our calendars every now and then. If you care about being precise, you care about leap seconds. And if you're writing software for others to use, chances are at least one of your users will be affected by DST at some point.

## <a name="Days_are_24_hours_long"></a>Days are 24 hours long

False. Many places around the world observe Daylight Saving Time, which means that people living in these locations will sometimes experience 23 hour days (when they "leap forward") and 25 hour days (when they "leap back").

## <a name="An_hour_will_never_occur_twice_in_a_single_day"></a>An hour will never occur twice in a single day

False. On days when we "leap back" for the Daylight Saving Time shift, one hour occurs *twice*. For example, in the United States, the hour that occurs twice is the 1 AM hour. This means that on these "fall back" days, correctly-implemented clocks will go from 1:58 ... 1:59 ... 1:00 ... 1:01 ... ... 1:59 ... 2:00 ... 2:01 ...

This leads to some interesting questions: If a user has set an alarm to wake up at 1 AM on that day, what happens? Does the alarm go off the hour after the midnight hour? Or does it go off during the hour before 2 AM? Or does it go off twice? Or do you just give up and not make the alarm go off at all and make your users miss their dead-of-night appointment?

## <a name="Every_day_has_a_midnight"></a>Every day has a midnight

False. Brazil performs its DST "leap forward" transition at midnight, which means that 11:59 PM is followed by 1:00 AM.

So if you're writing code and are trying to use the time `00:00:00` to represent "no time", you will be wrong in Brazil, and [Lebanon in 2017](https://www.timeanddate.com/time/change/lebanon?year=2017).

## <a name="Days_start_ad_midnight_or_as_close_to_it_as_possible"></a>Days start at midnight (or as close to it as possible)

Mostly true. For the sake of simplifying calculations and establishing conventions, the day-to-day rollover happens at midnight. However, the Hebrew calendar traditionally starts its days at sunset.

## <a name="Saturday_and_Sunday_are_the_weekend"></a>Saturday and Sunday are the weekend

False. Most muslim countries use either Thursday and Friday, or Friday and Saturday as their weekend.

## <a name="Weeks_start_on_Sunday"></a>Weeks start on Sunday

False. Weeks start on Sunday in the United States, Monday in Europe, and a couple of places start on Saturday.

## <a name="Days_in_a_work_week_are_always_contiguous"></a>Days in a work week are always contiguous

False. In Brunei, the work week is Monday - Thursday and Saturday.

## <a name="Everyone_uses_the_Gregorian_calendar"></a>Everyone uses the Gregorian calendar

False. Many places in Africa use one of the various [Coptic calendars](https://en.wikipedia.org/wiki/Coptic_calendar). Israel uses the [Hebrew calendar](https://en.wikipedia.org/wiki/Hebrew_calendar) for determining holidays. The [Islamic calendar](https://en.wikipedia.org/wiki/Islamic_calendar) is used all through the Middle East and other predominantly muslim countries. Thailand uses the Buddhist calendar. Japan uses the [Japanese Imperial calendar](https://en.wikipedia.org/wiki/Japanese_calendar) for official state business.

## <a name="Months_always_have_30_or_31_days_in_them"></a>Months always have 30 or 31 days in them

False. February. Duh.

## <a name="Ok_Months_always_have_at_least_28_days_in_them"></a>OK... Months always have at least 28 days in them

False. The month [*Pi Kogi Enavot*](https://en.wikipedia.org/wiki/Intercalary_month_%28Egypt%29) in the [Coptic calendar](https://en.wikipedia.org/wiki/Coptic_calendar) only has 5 or 6 days in it (depending on the year).

## <a name="Month_lengths_follow_regular_cycles"></a>Month lengths follow regular cycles

Mostly true, but specifically false. Traditional [Islamic calendars](https://en.wikipedia.org/wiki/Islamic_calendar) base their months on local observations of the moon. Sighting the moon determines whether the month will be 29 or 30 days long. However, since you can't know ahead of time if the moon will be visible (for example: extreme cloud cover), it's not always possible to know ahead of time how long the month will be.

## <a name="A_week_is_always_seven_days"></a>A week is always seven days

Currently true, but historically false. A couple of out-of-use calendars, like the [Decimal calendar](https://en.wikipedia.org/wiki/Decimal_time) and the [Egyptian calendar](https://en.wikipedia.org/wiki/Egyptian_calendar#Lunar_calendar) had weeks that were 7, 8, or even 10 days.

## <a name="The_current_year_is_2017"></a>The current year is 2017

False. It's the year 5777 in the [Hebrew calendar](https://en.wikipedia.org/wiki/Hebrew_calendar).

## <a name="All_the_important_years_are_four_digits_long"></a>All the important years are four digits long

False. It's the year Heisei 29 in the [Japanese calendar](https://en.wikipedia.org/wiki/Japanese_calendar).

## <a name="In_a_range_of_hours_an_hour_will_not_be_missing_in_the_middle_of_it"></a>In a range of hours, an hour will not be missing in the middle of it

False. When the "leap forward" transition happens for Daylight Saving Time, an hour is missing. In the US, this is the 2 AM hour, which means that time goes from 1:58 ... 1:59 ... 3:00 ... 3:01 ...

## <a name="In_a_range_of_days_a_day_will_not_be_missing_in_the_middle_of_it"></a>In a range of days, a day will not be missing in the middle of it

False. In 1582, the transition from the Julian to Gregorian calendars meant that there was about a week and a half that was missing for various locations around Europe. That same switch happened in the [United States in 1752](https://en.wikipedia.org/wiki/Adoption_of_the_Gregorian_calendar).

Additionally, in 2011, Samoa decided to jump "ahead" a full day in order to move to the west side of the International Date Line (previously they were on the east). This resulted in December 30, 2011 being skipped on their calendars. So for residents of Samoa, December 29, 2011 was followed by December 31, 2011. The Marshall Islands made [the same move in 1993](http://www.nytimes.com/1993/08/22/world/in-marshall-islands-friday-is-followed-by-sunday.html).

## <a name="In_a_range_of_months_a_month_will_not_be_missing_in_the_middle_of_it"></a>In a range of months, a month will not be missing in the middle of it

False. The [Hebrew calendar](https://en.wikipedia.org/wiki/Hebrew_calendar) uses leap months, which occur [during the middle of the year](https://en.wikipedia.org/wiki/Adar).

## <a name="A_year_is_twelve_months"></a>A year is twelve months

False. Calendars like the [Hebrew](https://en.wikipedia.org/wiki/Hebrew_calendar) and [Coptic](https://en.wikipedia.org/wiki/Coptic_calendar) calendars deal with years that are 13 months long.

## <a name="A_year_is_365_or_366_days"></a>A year is 365 (or 366) days

False. The [Islamic calendar](https://en.wikipedia.org/wiki/Islamic_calendar) is 354 (or 355) days long.

## <a name="A_holiday_will_always_occur_in_the_same_part_of_the_solar_year"></a>A holiday will always occur in the same part of the solar year

False. Because the Islamic calendar is only 354 days long, holidays drift by about 10 days each solar year. So after eighteen years, a holiday that used to occur during the winter will be in the summer.

## <a name="Leap_years_occur_every_four_years"></a>Leap years occur every four years

False. The year 1900 was not a leap year.

## <a name="Leap_years_occur_every_four_years_except_when_the_year_is_evenly_divisible_by_100"></a>Leap years occur every four years except when the year is evenly divisible by 100

False. The year 2000 *was* a leap year.

## <a name="Leap_years_occur_every_four_years_except_when_the_year_is_evenly_divisible_by_100_unless_it_s_also_evenly_divisible_by_400"></a>Leap years occur every four years except when the year is evenly divisible by 100, unless it's also evenly divisible by 400.

False. The [Hebrew calendar](https://en.wikipedia.org/wiki/Hebrew_calendar), which is based almost entirely off the lunar cycle, inserts leap years [7 times in a 19 year period](https://en.wikipedia.org/wiki/Hebrew_calendar#Leap_years).

## <a name="The_current_year_only_changes_at_New_Years"></a>The current year only changes at "New Years"

False. The current year of the [Japanese Imperial calendar](https://en.wikipedia.org/wiki/Japanese_calendar) is based on the reign of the current emperor. When the emperor dies (or abdicates), the next day is reset to the year 1 (of a new era).

For example, the Emperor Shōwa (Hirohito) passed away on January 7, Shōwa 64 (January 7, 1989). His son, Akihito, ascended to the throne the next day, which was the date January 8, Heisei 1.

## <a name="A_year_only_has_one_New_Years"></a>A year only has one "New Years"

False. In addition to the Japanese calendar having (potentially) an unbounded number of "New Years" in a single year, the [Hebrew calendar](https://en.wikipedia.org/wiki/Hebrew_calendar#New_year) historically celebrated up to *four* different New Years in a single year.

## <a name="Nobody_uses_the_Julian_calendar_anymore"></a>Nobody uses the Julian calendar anymore

False. The Julian calendar is still used by Eastern Orthodox churches, and the Julian day is used in certain kinds of astronomical calculations.

## <a name="Timezones_always_are_on_the_hour_mark"></a>Timezones always are on the hour mark

False. Many places have half-hour offsets, such as French Polynesia, Newfoundland and Labrador, Iran, Afghanistan, India, Sri Lanka, Myanmar, the Cocos Islands, North Korea, and parts of Australia.

## <a name="OK_Timezones_are_always_on_the_half_hour_mark"></a>OK... Timezones are always on the *half* hour mark

False. There are a few places that have an offset of :15 of :45 minutes, such as Nepal, part of Western Australia, and the Chatham Islands.

## <a name="Fine_Timezones_are_always_on_the_quarter_hour_mark"></a>*Fine*... Timezones are always on the *quarter* hour mark

Currently true, but historically false. Before the advent of global communications and standarized time keeping, the current time was pretty much up to the local administrators. When regions were brought in line with the international time keeping standards, they'd have to do some shifts to accomplish that, like Shanghai's weird 343 second shift in the early 1900s. For more examples, Liberia was [44 minutes behind UTC](https://en.wikipedia.org/wiki/UTC−00:44) up until 1972, and from 1880 to 1916, Ireland was [25 minutes and 21 seconds behind UTC](https://en.wikipedia.org/wiki/UTC-00:25:21).

## <a name="No_place_is_ever_more_than_12_hours_away_from_UTC"></a>No place is ever more than 12 hours away from UTC

False. Parts of [Oceania](https://en.wikipedia.org/wiki/Oceania) are 12:45, 13:00, and 14:00 hours ahead of UTC.

## <a name="No_location_will_ever_change_what_time_zone_it_s_in"></a>No location will ever change what time zone it's in

False. As mentioned above, Samoa did just that in 2011. Cancún [switched timezones in 2015](http://abcnews.go.com/Travel/cancun-change-eastern-standard-time/story?id=28589197), as did [Turks & Caicos](http://www.huffingtonpost.com/2015/03/09/turks-and-caicos-time-zone_n_6832054.html).

## <a name="We_re_done_adding_time_zones"></a>We're done adding time zones.

False. The `Asia/Tomsk` timezone [was created in 2016](http://linuxsoft.cern.ch/cern/slc57/i386/yum/updates/repoview/tzdata.html) for parts of eastern Russia.

## <a name="Time_zones_do_not_change_their_offset_from_UTC"></a>Time zones do not change their offset from UTC

False. [Eight different time zones changed their UTC offset](http://linuxsoft.cern.ch/cern/slc57/i386/yum/updates/repoview/tzdata.html) in 2016.

## <a name="The_UNIX_epoch_is_January_1_1970"></a>The UNIX epoch is January 1, 1970

False. The UNIX epoch is January 1, 1970 in UTC, but is Dec 31, 1969 in Los Angeles.

## <a name="Daylight_Saving_Time_rules_do_not_change"></a>Daylight Saving Time rules do not change

False. They change all the time. In 2016, there were [nine different DST changes](http://linuxsoft.cern.ch/cern/slc57/i386/yum/updates/repoview/tzdata.html).

## <a name="Daylight_Saving_Time_rules_do_not_change_on_short_notice"></a>Daylight Saving Time rules do not change on short notice.

False. In 2016, Egypt decided to re-instate DST in June, and then reversed that decision three weeks later, [three days before the shift was supposed to happen](https://www.washingtonpost.com/news/worldviews/wp/2016/07/06/egypt-cancelled-daylight-savings-time-three-days-before-it-was-due-to-start/).

## <a name="It_is_normal_that_the_Sept_Oct_Nov_and_Dec_months_are_numbered_9_10_11_and_12"></a>It is normal that the Sept-, Oct-, Nov-, and Dec- months are numbered 9, 10, 11, and 12

False. This is very weird. They used to be months 7, 8, 9, and 10, but some [reform to the Roman calendar](https://en.wikipedia.org/wiki/Roman_calendar#Calendar_of_Numa) back in the day resulted in the creation of January and February, which messed everything up.

## <a name="Everything_you_know_about_calendars_is_applicable_to_space_travel"></a>Everything you know about calendars is applicable to space travel.

False. There are many weird things about calendars and space travel. Days are longer, days are shorter, time flows faster, time flows slower, days are longer than years, etc etc.

## <a name="Calendrical_isn't_a_real_word"></a>"Calendrical" isn't a real word.

[False](https://www.merriam-webster.com/dictionary/calendrical).

## <a name="This_is_all_really_complicated"></a>This is all really complicated.

True!

## <a name="I_never_want_to_write_code_that_handles_all_of_this"></a>I never want to write code that handles all of this.

True! You should always use the Date and Time Services provided by the [ICU Project](http://userguide.icu-project.org/datetime). If you're an iOS/macOS developer, then you should always stick to `NSCalendar` and its cohorts, which are all built on top of the ICU libraries.

