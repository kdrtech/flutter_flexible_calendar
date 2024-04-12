<!-- 
This README describes the package. If you publish this package to pub.dev,
this README's contents appear on the landing page for your package.

For information about how to write a good package README, see the guide for
[writing package pages](https://dart.dev/guides/libraries/writing-package-pages). 

For general information about developing packages, see the Dart guide for
[creating packages](https://dart.dev/guides/libraries/create-library-packages)
and the Flutter guide for
[developing packages and plugins](https://flutter.dev/developing-packages). 
-->


# flutter_flexible_calendar

[![Pub Package](https://img.shields.io/pub/v/flutter_flexible_calendar.svg?style=flat-square)](https://pub.dev/packages/flutter_flexible_calendar)

<a  href="https://www.buymeacoffee.com/kdrtech" target="_blank">
<img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" height="41" />
</a>

Highly video, feature-packed flutter_flexible_calendar widget for Flutter.


| ![Image](https://raw.githubusercontent.com/kdrtech/flutter_flexible_calendar/master/example/assets/standard.gif)
| :------------: |
| **Standard** |

| ![Image](https://raw.githubusercontent.com/kdrtech/flutter_flexible_calendar/master/example/assets/horizontal.gif)
| :------------: |
| **Horizontal** |

| ![Image](https://raw.githubusercontent.com/kdrtech/flutter_flexible_calendar/master/example/assets/single.gif)
| :------------: |
| **Single selected** |

| ![Image](https://raw.githubusercontent.com/kdrtech/flutter_flexible_calendar/master/example/assets/multiple.gif)
| :------------: |
| **Multiple select** |

## Features

* Standar calendar user interface
* Hotizontal calendar user interface 
* Calendar header change month and year.
* New Feature: Support the multiple select  the same month.
* New Feature: Support range select with default start select and end select the same month.
* New Feature: Support set default single select date.

## Usage

Make sure to check out [examples](https://github.com/kdrtech/flutter_flexible_calendar/tree/master/example/lib)


### Installation

Add the following line to `pubspec.yaml`:

```yaml
dependencies:
  flutter_flexible_calendar: ^1.0.0
```

### Basic setup

*The complete example is available [here](https://github.com/kdrtech/flutter_flexible_calendar/tree/master/example/lib).*

***&#11088;Standard Calendar***
```dart
 FlutterFlexibleCalendarView(
    showHeader: true,
    headerBgColor: Colors.white38,
    calendarType: FlutterFlexibleCalendarType.standard,
    showWeekendDay: false,
    disabledPreDay: true,
    colorBg: Colors.transparent,
    maxLimitYear: 2,
    minLimitYear: 2,
    month: DateTime(_currentMonth.year, _currentMonth.month, 1),
    didResult: (item, datetime) {
      print("itme: ${item?.date}");
      print("itme: ${item?.dateTime}");
      print("itme: ${item?.nameOffWeek}");
      print("date: ${datetime?.day}");
      print("date: ${datetime?.month}");
      print("date: ${datetime?.year}");
    },
    didDisableItemClick: () {},
    didWeekendItemClick: () {},
)
```
***&#11088;Horizontal Calendar***
```dart
 FlutterFlexibleCalendarView(
    showHeader: true,
    headerBgColor: Colors.white38,
    calendarType: FlutterFlexibleCalendarType.horizontal,
    showWeekendDay: false,
    disabledPreDay: true,
    colorBg: Colors.transparent,
    maxLimitYear: 2,
    minLimitYear: 2,
    month: DateTime(_currentMonth.year, _currentMonth.month, 1),
    didResult: (item, datetime) {
      print("itme: ${item?.date}");
      print("itme: ${item?.dateTime}");
      print("itme: ${item?.nameOffWeek}");
      print("date: ${datetime?.day}");
      print("date: ${datetime?.month}");
      print("date: ${datetime?.year}");
    },
    didDisableItemClick: () {},
    didWeekendItemClick: () {},
)
```
***&#11088;Single Select***
```dart
 FlutterFlexibleCalendarView(
    showHeader: true,
    headerBgColor: Colors.white38,
    calendarType: FlutterFlexibleCalendarType.standard,
    showWeekendDay: false,
    disabledPreDay: true,
    colorBg: Colors.transparent,
    maxLimitYear: 2,
    minLimitYear: 2,
    month: DateTime(_currentMonth.year, _currentMonth.month, 1),
    isMultipleSelected: false,
    currentSelected: DateTime(2024, 4, 24),
    didResult: (item, datetime) {
     if (kDebugMode) {
        print(
            "date selected: ${item?.date}, ${item?.dateTime}, ${item?.nameOffWeek}");
      }
    },
    didDisableItemClick: () {},
    didWeekendItemClick: () {},
)
```
***&#11088;Multiple Select***
```dart
 FlutterFlexibleCalendarView(
    showHeader: true,
    headerBgColor: Colors.white38,
    calendarType: FlutterFlexibleCalendarType.standard,
    showWeekendDay: false,
    disabledPreDay: true,
    colorBg: Colors.transparent,
    maxLimitYear: 2,
    minLimitYear: 2,
    month: DateTime(_currentMonth.year, _currentMonth.month, 1),
    isMultipleSelected: true,
    setStartSelected: DateTime(2024, 4, 13),
    setEndSelected: DateTime(2024, 4, 19),
    didResult: (item, datetime) {
      if (kDebugMode) {
        print(
            "date selected: ${item?.date}, ${item?.dateTime}, ${item?.nameOffWeek}");
      }
    },
    didMultipleSelected: (firstDate, lastDate) {
      if (kDebugMode) {
        print(
            "firstDate: ${firstDate?.date}, ${firstDate?.dateTime}, ${firstDate?.nameOffWeek}");
        print(
            "lastDate: ${lastDate?.date}, ${lastDate?.dateTime}, ${lastDate?.nameOffWeek}");
      }
    },
    didDisableItemClick: () {},
    didWeekendItemClick: () {},
)
```
### Parameter
```dart
* showHeader : show calendar header. 
* headerBgColor : set header background color.
* calendarType : set calendar type (horizontal, standard)
* showWeekendDay: show weekend day of previous of the month. 
* disabledPreDay: disabled previous day.
* colorBg: set calendar background color.
* maxLimitYear: set max year allow move next.
* minLimitYear: set min year allow move back.
* month: set default month of calendar.
* didResult: function to return date selected.
* didDisableItemClick: function to return status when click on disabled item.
* didWeekendItemClick: function to return status when click on weekend of day.
* headerArrowLeft: allow change arrow left header icon.
* headerArrowRight: allow change arrow right header icon.
* isMultipleSelected : allow set multiple select (true , false)
* setStartSelected: set default start date select(Ex:  DateTime(2024, 4, 13))
* setEndSelected: set default end date select(Ex:  DateTime(2024, 4, 19))
* currentSelected: set default single date select(Ex: DateTime(2024, 4, 24))
* other you can check our class.
  ```
### Events

use `didResult` to return date user selected.

```dart
didResult: (item, datetime) {

}
```

use `didDisableItemClick` to return status user click on disabled item date.

```dart
didDisableItemClick: () {

}
```

use `didWeekendItemClick` to return status user click on item date weekend of previous of the month.

```dart
didWeekendItemClick: () {

}
```

use `didMultipleSelected` to return first date select and last date select.

```dart
didMultipleSelected: (firstDate, lastDate) {

}
```

Hello everyone 👋

If you want to support me, feel free to do so. 

Thanks

============================================

សួស្ដី អ្នកទាំងអស់គ្នា👋 

បើ​អ្នក​ចង់​គាំទ្រ​ខ្ញុំ សូម​ធ្វើ​ដោយ​សេរី , 

សូមអរគុណ

<a  href="https://www.buymeacoffee.com/kdrtech" target="_blank">
<img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" height="41" />
</a>
