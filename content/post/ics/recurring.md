---
title: "ics file reference for recurring events"
date: 2020-09-08T17:25:59+08:00
draft: false
lastmod: 2020-09-08T17:25:59+08:00
tags: ["calendar", "ics", "recurring"]
categories: ["Calendar"]
---

# Introduction

Just an experiment

<!--more-->

## Modification

### Variations tried

* A - first edition of the chain
    * 1 - edit #1
    * 2 - edit #3
    * 3 - delete #1
    * 4 - delete #3
* B - Already edited #1 (single edit) 
    * 1 - edit #3
    * 2 - edit #5
    * 3 - delete #1
    * 4 - delete #3
    * 5 - delete #5
* C - Already edited #3 (single edit) 
    * 1 - edit #1
    * 2 - edit #5
    * 3 - delete #1
    * 4 - delete #3
    * 5 - delete #5
* D - Already deleted #1 (single edit) 
    * 1 - edit #3
    * 2 - delete #3
* E - Already deleted #3 (single edit) 
    * 1 - edit #1
    * 2 - edit #5
    * 3 - delete #1
    * 4 - delete #5
* F - Already edited #5 (This and future) 
    * 1 - edit #1
    * 2 - edit #3
    * 3 - edit #5
    * 4 - edit #7
    * 5 - delete #1
    * 6 - delete #3
    * 7 - delete #5
    * 8 - delete #7

## A1 

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY
DTSTAMP:20200908T095333Z
UID:4tc3orf8sp20ont4ke7ke60hnb@google.com
CREATED:20200908T095320Z
DESCRIPTION:
LAST-MODIFIED:20200908T095320Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT
```

### This

#### Change time

Add 1 hour to start time

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY
DTSTAMP:20200908T095849Z
UID:0eusa8deak15brd6almjnk3s7a@google.com
CREATED:20200908T095812Z
DESCRIPTION:
LAST-MODIFIED:20200908T095812Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT

BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T110000
DTEND;TZID=Asia/Taipei:20200908T120000
DTSTAMP:20200908T095849Z
UID:0eusa8deak15brd6almjnk3s7a@google.com
RECURRENCE-ID;TZID=Asia/Taipei:20200908T100000
CREATED:20200908T095812Z
DESCRIPTION:
LAST-MODIFIED:20200908T095821Z
LOCATION:
SEQUENCE:1
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT
```

#### Change summary to 11

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY
DTSTAMP:20200908T095417Z
UID:4tc3orf8sp20ont4ke7ke60hnb@google.com
CREATED:20200908T095320Z
DESCRIPTION:
LAST-MODIFIED:20200908T095320Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT

BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
DTSTAMP:20200908T095417Z
UID:4tc3orf8sp20ont4ke7ke60hnb@google.com
RECURRENCE-ID;TZID=Asia/Taipei:20200908T100000
CREATED:20200908T095320Z
DESCRIPTION:
LAST-MODIFIED:20200908T095407Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:11
TRANSP:OPAQUE
END:VEVENT
```

### This and future

#### Change time

Add 1 hour to start time

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T110000
DTEND;TZID=Asia/Taipei:20200908T120000
RRULE:FREQ=DAILY
DTSTAMP:20200908T095934Z
UID:7urik0e1c7vpq160mi50fckn5v@google.com
CREATED:20200908T095925Z
DESCRIPTION:
LAST-MODIFIED:20200908T095927Z
LOCATION:
SEQUENCE:1
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT
```

#### Change summary to 111

##### From change to 11 (single edit) to this state

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY
DTSTAMP:20200908T100127Z
UID:71nroj8inhmqoa6beebr6jkdf4@google.com
CREATED:20200908T100104Z
DESCRIPTION:
LAST-MODIFIED:20200908T100120Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:111
TRANSP:OPAQUE
END:VEVENT

BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
DTSTAMP:20200908T100127Z
UID:71nroj8inhmqoa6beebr6jkdf4@google.com
RECURRENCE-ID;TZID=Asia/Taipei:20200908T100000
CREATED:20200908T100104Z
DESCRIPTION:
LAST-MODIFIED:20200908T100120Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:111
TRANSP:OPAQUE
END:VEVENT
```

##### From a new event -> change directly to this state

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY
DTSTAMP:20200908T095607Z
UID:6is9r3je6oa9kupeq3d8gdftjj@google.com
CREATED:20200908T095552Z
DESCRIPTION:
LAST-MODIFIED:20200908T095558Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:111
TRANSP:OPAQUE
END:VEVENT
```

### All

#### Change time

Add 1 hour to start time

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T110000
DTEND;TZID=Asia/Taipei:20200908T120000
RRULE:FREQ=DAILY
DTSTAMP:20200908T100016Z
UID:46oevddkqjtrgm6gn7uq9tc1ih@google.com
CREATED:20200908T100003Z
DESCRIPTION:
LAST-MODIFIED:20200908T100007Z
LOCATION:
SEQUENCE:1
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT
```

#### Change summary to 1111

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY
DTSTAMP:20200908T095724Z
UID:29ilmrr00mah4kopesg2i0ljqt@google.com
CREATED:20200908T095714Z
DESCRIPTION:
LAST-MODIFIED:20200908T095719Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:1111
TRANSP:OPAQUE
END:VEVENT
```

## A2

```

```

### This

#### Change summary to 11

```

```

#### Change time

```

```

### This and future

#### Change summary to 111

Delete all will delete `47f2valst6du690d43riojoa7o@google.com` and `47f2valst6du690d43riojoa7o_R20200910T023000@google.com`

```

```

#### Change time

```

```

### All

#### Change summary to 1111

Delete all will delete `47f2valst6du690d43riojoa7o@google.com` and `47f2valst6du690d43riojoa7o_R20200910T023000@google.com`

```

```

#### Change time

```

```

## A3

### This

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY
EXDATE;TZID=Asia/Taipei:20200908T100000
DTSTAMP:20200908T103532Z
UID:3tqm0jflv1ecdcc9k9uun4mn71@google.com
CREATED:20200908T103459Z
DESCRIPTION:
LAST-MODIFIED:20200908T103459Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT
```

No `this and future` and `all` available.

## A4

### This

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY
EXDATE;TZID=Asia/Taipei:20200910T100000
DTSTAMP:20200908T104756Z
UID:3bs26ptgd106p53fqclk33osst@google.com
CREATED:20200908T104745Z
DESCRIPTION:
LAST-MODIFIED:20200908T104745Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT
```

### This and future

```
BEGIN:VEVENT
DTSTART;TZID=Asia/Taipei:20200908T100000
DTEND;TZID=Asia/Taipei:20200908T110000
RRULE:FREQ=DAILY;UNTIL=20200909T155959Z
DTSTAMP:20200908T104831Z
UID:59k4fm40644l9m5l21mfrn97du@google.com
CREATED:20200908T104821Z
DESCRIPTION:
LAST-MODIFIED:20200908T104825Z
LOCATION:
SEQUENCE:0
STATUS:CONFIRMED
SUMMARY:1
TRANSP:OPAQUE
END:VEVENT
```

No `all` available.

## B1

### This

```

```

### This and future

```

```

### All

```

```

## B2

### This

```

```

### This and future

```

```

### All

```

```

## B3

### This

```

```

### This and future

```

```

### All

```

```

## B4

### This

```

```

### This and future

```

```

### All

```

```

## B5

### This

```

```

### This and future

```

```

### All

```

```

## C1

### This

```

```

### This and future

```

```

### All

```

```

## C2

### This

```

```

### This and future

```

```

### All

```

```

## C3

### This

```

```

### This and future

```

```

### All

```

```

## C4

### This

```

```

### This and future

```

```

### All

```

```

## C5

### This

```

```

### This and future

```

```

### All

```

```

## D1

### This

```

```

### This and future

```

```

### All

```

```

## D2

### This

```

```

### This and future

```

```

### All

```

```


## E1 

### This

```

```

### This and future

```

```

### All

```

```

## E2

### This

```

```

### This and future

```

```

### All

```

```

## E3

### This

```

```

### This and future

```

```

### All

```

```

## E4

### This

```

```

### This and future

```

```

### All

```

```

## F1

### This

```

```

### This and future

```

```

### All

```

```

## F2

### This

```

```

### This and future

```

```

### All

```

```

## F3

### This

```

```

### This and future

```

```

### All

```

```

## F4

### This

```

```

### This and future

```

```

### All

```

```

## F5

### This

```

```

### This and future

```

```

### All

```

```

## F6

### This

```

```

### This and future

```

```

### All

```

```

## F7

### This

```

```

### This and future

```

```

### All

```

```

## F8

### This

```

```

### This and future

```

```

### All

```

```