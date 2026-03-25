# Brief Description
This is a period library/class that contains 12 functions which perform 7 different functionalities to manipulate periods in `Cpp`.
A period , is the time between two dates. 

# Purpose
The purpose of this project is mainly to practice OOP.
The project is related to [ProgrammingAdvices Roadmap](https://programmingadvices.com/p/roadmap) - Course 10 - Project Number 02.
Feel free to check my notes/projects about this course [Course 10](https://github.com/YasinHamad/Programming_Basics/tree/main/course_10), and other courses [Programming Basics](https://github.com/YasinHamad/Programming_Basics).

# Table of Content

- [Brief Description](# Brief Description)
- [Purpose](# Purpose)
- [Constructors](# Constructors)
- [Getters, Setters, and Properties](# Getters, Setters, and Properties)
- [Functionalities](# Functionalities)

# Constructors
How to create an object form this class?

```cpp
clsPeriod _test_period_1(clsDate(1, 10, 2026), clsDate(10, 10, 2026));
cout << _test_period_1.ToString() << "\n";
```

```output
{
        StartDate: {Day:1, Month: 10, Year:2026},
        EndDate  : {Day:10, Month: 10, Year:2026}
}
```

# Getters, Setters, and Properties

```cpp
clsDate getStartDate();
void setStartDate(clsDate StartDate);
__declspec(property(get = getStartDate, put = setStartDate)) clsDate starDate;

clsDate getEndDate();
void setEndDate(clsDate EndDate);
__declspec(property(get = getEndDate, put = setEndDate)) clsDate endDate;
```

# Functionalities
## Functionality #1
`static bool IsOverlapedPeriods(clsPeriod period1, clsPeriod period2);`
`bool IsOverlapedWith(clsPeriod period);`

<u>Inputs :</u>
The periods objects we want to work on.

<u>Outputs :</u>
`bool` : do periods have days in common? or not.

<u>Explanation :</u>
These functions check whether two periods have days in common or not.

<u>Example of Usage :</u>
```cpp
clsPeriod _test_period_1(clsDate(1, 10, 2026), clsDate(10, 10, 2026));
clsPeriod _test_period_2(clsDate(5, 10, 2026), clsDate(10, 10, 2026));
clsPeriod _test_period_3(clsDate(20, 10, 2026), clsDate(25, 10, 2026));

cout << _test_period_1.IsOverlapedWith(_test_period_2) << "\n";
cout << clsPeriod::IsOverlapedPeriods(_test_period_1, _test_period_3);
```

```output
1
0
```

## Functionality #2
`static string ToString(clsPeriod period);`
`string ToString();`

<u>Inputs :</u>
The period object we want to work on.

<u>Outputs :</u>
The period object as string.

<u>Explanation :</u>
These functions return a period object as string.

<u>Example of Usage :</u>
```cpp
clsPeriod _test_period_1(clsDate(1, 10, 2026), clsDate(10, 10, 2026));
clsPeriod _test_period_2(clsDate(5, 10, 2026), clsDate(10, 10, 2026));

cout << _test_period_1.ToString() << "\n";
cout << clsPeriod::ToString(_test_period_2) << "\n";
```

```output
{
        StartDate: {Day:1, Month: 10, Year:2026},
        EndDate  : {Day:10, Month: 10, Year:2026}
}
{
        StartDate: {Day:5, Month: 10, Year:2026},
        EndDate  : {Day:10, Month: 10, Year:2026}
}
```

## Functionality #3
`static clsPeriod ReadPeriod();`

<u>Inputs :</u>
Nothing.

<u>Outputs :</u>
`clsPeriod` : is the object read form screen.

<u>Explanation :</u>
This function read a `clsPeriod` object from screen.

<u>Example of Usage :</u>
```cpp
cout << (clsPeriod::ReadPeriod()).ToString() << "\n";
```

```output
Filling a period:
Filling start date:

Enter a date: 1
Enter a month: 1
Enter a year: 2022

Filling end date:

Enter a date: 1
Enter a month: 1
Enter a year: 2026

{
        StartDate: {Day:1, Month: 1, Year:2022},
        EndDate  : {Day:1, Month: 1, Year:2026}
}
```

## Functionality #4
`static int PeriodLengthInDays(clsPeriod period, bool include_last_day = false);`
`int PeriodLengthInDays(bool include_last_day = false);`

<u>Inputs :</u>
`clsPeriod` : is the period we want to work on.
`bool include_last_day` : is by default false.

<u>Outputs :</u>
`int` : the period object's length in days.

<u>Explanation :</u>
These functions return the length of a period object in days.

<u>Example of Usage :</u>
```cpp
clsPeriod _test_period_1(clsDate(1, 10, 2026), clsDate(10, 10, 2026));
clsPeriod _test_period_2(clsDate(5, 10, 2026), clsDate(10, 10, 2026));

cout << _test_period_1.PeriodLengthInDays() << "\n";
cout << clsPeriod::PeriodLengthInDays(_test_period_2, true) << "\n";
```

```output
9
6
```

## Functionality #5
`static bool IsDateWithinPeriod(clsDate date, clsPeriod period);`
`bool IsDateWithinPeriod(clsDate date);`

<u>Explanation :</u>
These functions check whether a specific date within a period or not.

<u>Example of Usage :</u>
```cpp
clsPeriod _test_period_1(clsDate(1, 10, 2026), clsDate(10, 10, 2026));

cout << _test_period_1.IsDateWithinPeriod(clsDate(5, 10, 2026)) << "\n";
cout << clsPeriod::IsDateWithinPeriod(clsDate(20, 12, 2026), _test_period_1) << "\n";
```

```output
1
0
```

## Functionality #6
`static void SwitchPeriods(clsPeriod& period1, clsPeriod& period2);`

<u>Explanation :</u>
This function switch two periods.	

<u>Example of Usage :</u>
```cpp
clsPeriod _test_period_1(clsDate(1, 10, 2026), clsDate(10, 10, 2026));
clsPeriod _test_period_2(clsDate(5, 10, 2026), clsDate(10, 10, 2026));

cout << _test_period_1.ToString() << "\n";
cout << _test_period_2.ToString() << "\n";

clsPeriod::SwitchPeriods(_test_period_1, _test_period_2);

cout << _test_period_1.ToString() << "\n";
cout << _test_period_2.ToString() << "\n";
```

```output
{
        StartDate: {Day:1, Month: 10, Year:2026},
        EndDate  : {Day:10, Month: 10, Year:2026}
}
{
        StartDate: {Day:5, Month: 10, Year:2026},
        EndDate  : {Day:10, Month: 10, Year:2026}
}
{
        StartDate: {Day:5, Month: 10, Year:2026},
        EndDate  : {Day:10, Month: 10, Year:2026}
}
{
        StartDate: {Day:1, Month: 10, Year:2026},
        EndDate  : {Day:10, Month: 10, Year:2026}
}
```

## Functionality #7
`static int CountOverlapDays(clsPeriod period1, clsPeriod period2);`
`int CountOverlapDays(clsPeriod period);`

<u>Explanation :</u>
These functions count the days between two periods.

<u>Example of Usage :</u>
```cpp
clsPeriod _test_period_1(clsDate(1, 10, 2026), clsDate(10, 10, 2026));
clsPeriod _test_period_2(clsDate(5, 10, 2026), clsDate(10, 10, 2026));
clsPeriod _test_period_3(clsDate(20, 10, 2026), clsDate(25, 10, 2026));

cout << _test_period_1.CountOverlapDays(_test_period_2) << "\n";
cout << clsPeriod::CountOverlapDays(_test_period_1, _test_period_3) << "\n";
```

```output
6
0
```