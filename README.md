# bulma-calendar - fork by meta-system
Bulma's extension to display a calendar. It can be used on page as large calendar with apointments or in modal/popup for datepicker.

**This is a private fork of the original [bulma-calendar](https://github.com/Wikiki/bulma-calendar) with some fixes
needed by company meta-system!**

This fork contains several branches, which contain various fixes. Some of them are PRs at upstream.
The `master` branch in this fork is derived from original commit
[c7e6303](https://github.com/Wikiki/bulma-calendar/commit/c7e6303ee59b4833c8dd4ce80195aa28e414d59c)
(aka bulma-calendar release [v6.1.19](https://github.com/Wikiki/bulma-calendar/releases/tag/v6.1.19)) 
and does *not* contain any further changes. All changes are in separate `bugfix` branches and in the
branch `feature/all-meta-system-changes`, which contains all collected bugfixes.

### Bugfix branches made by meta-system

* `bugfix/typescript-issues` fixes some typescript definitions
* `bugfix/issue-196-set-min-max-date-and-refresh` fixes a quirk reported in
  [#196](https://github.com/Wikiki/bulma-calendar/issues/196#issuecomment-823881530)
* `bugfix/issue-315-remove-event-handlers-on-destroy` fixes [#315](https://github.com/Wikiki/bulma-calendar/issues/315)


# How to build this fork locally

**Node.js 16.x / NPM 8.x is required to build!** Higher versions have problems with the build chain currently.
Build dependencies must be updated; this is a future task.

Run `npm install --legacy-peer-deps` to install dependencies.

Then run `npm run build` to build all artifacts.

To run the demo, `ruby` and the ruby bundler `bundle` is required. Both must
be installed locally and be available in your system path. Then run:
```sh
bundle config set --local path '.ruby/vendor/bundle'  # must be done only once
bundle install                                        # only after update of deps
npx gulp demo
```

# Examples

### Date format

```js
var calendars = new bulmaCalendar('.bulmaCalendar', {
    dateFormat: 'dd.MM.yyyy' // 01.01.2021
});
```

where `dateFormat` is a string with a combination of this values:

```
d: short day (1-31)
dd: long day (00-31)
EEE: short weekday (es: Mon)
EEEE: long weekday (es: Monday)
M: short month (1-12)
MM: long month (01-12)
MMM: short month name (es: Jan, Feb)
MMMM: full month name (es: January)
yy: short year (18)
yyyy: full year (2018)
```

For more values take a look at the [date-fns 2.x format](https://date-fns.org/v2.21.3/docs/format).

### Language

```js

var calendars = new bulmaCalendar('.bulmaCalendar', {
    lang: 'it' // refer to date-fns locales
});
```

### Default Options

Here's the options object and the default values as appears on code. For more options, please see the documentation.

```js
var defaultOptions = {
    color: 'primary',
    isRange: false,
    allowSameDayRange: true,
    lang: 'en-US',
    startDate: undefined,
    endDate: undefined,
    minDate: null,
    maxDate: null,
    disabledDates: [],
    disabledWeekDays: undefined,
    highlightedDates: [],
    weekStart: 0,
    dateFormat: 'MM/dd/yyyy',
    enableMonthSwitch: true,
    enableYearSwitch: true,
    displayYearsCount: 50,
};
```

# Documentation & Demo

You can find the full Documentation and a demo [here](https://doc.mh-s.de/bulma-calendar)
