# Russian Time Travel Problem within Julien or Gregorian era
Problem Statement:- Jaya invented a Time Machine and wants to test it by time-traveling to visit Russia on the Day of Programmer (the 256thday of the year) during a year in the inclusive range from 1700 to 2700. From 1700 to 1917 , Russia’s official calendar was the Julian Calendar since 1919 they used the Gregorian calendar system. The transition from the Julian to Gregorian calendar system occurred in 1918 , when the next day after 31 January was February 14 . This means that in 1918, February 14 was the 32nd day of the year in Russia. In both calendar systems, February is the only month with a variable amount of days; it has 29 days during a leap year, and 28 days during all other years. In the Julian calendar, leap years are divisible by 4 ; in the Gregorian calendar, leap years are either of the following:

Divisible by 400
Divisible by 4 and not divisible by 100
Given a year, y, find the date of the 256th day of that year according to the official Russian calendar during that year. Then print it in the format dd.mm.yyyy, where dd is the two-digit day, mm is the two-digit month, and yyyy is y.

For example, the given year is 1984.1984 is divisible by 4, so it is a leap year. The 256 day of a leap year after 1918 is September 12, so the answer is 12.9.1984. 

Function Description

Complete the programmerday function in the editor below. It should return a string representing the date of the 256th day of the year given.
programmerday has the following parameter(s):
year: an integer 
Input Format

A single integer denoting year y.
Output Format

Print the full date of programmerday during year y in the format dd.mm.yyyy, where dd is the two-digit day, mm is the two-digit month, and yyyy is y.
# Sample Input
```2017```

# Sample Output
```13.09.2017```
# Solution

```C++
#include <bits/stdc++.h>
using namespace std;

bool isLeap(int year, char calendar) {
    if (calendar == 'j') {
        return (year % 4 == 0);
    } else if (calendar == 'g') {
        return (year % 400 == 0 || (year % 4 == 0 && year % 100 != 0));
    }
    return false;
}
string getDay(int year) {
    string result;
    if (year >= 1700 && year <= 1917) { 
        bool leap = isLeap(year, 'j');
        if (leap) {
            result = "12.09." + to_string(year);
        } else {
            result = "13.09." + to_string(year);
        }
    } else if (year >= 1919 && year <= 2700) { 
        bool leap = isLeap(year, 'g');
        if (leap) {
            result = "12.09." + to_string(year);
        } else {
            result = "13.09." + to_string(year);
        }
    } else if (year == 1918) {
        result = "26.09.1918";
    } else {
        result = "Invalid Input";
    }
    return result;
}

int main() {
    int year;
    cin >> year;
    cout << getDay(year) << endl;

    return 0;
}
```