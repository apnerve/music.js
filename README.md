# music.js

## Use Teoria.js Instead

This library is no longer maintained. I recommend using the music theory library Teoria.js instead:
[https://github.com/saebekassebil/teoria](https://github.com/saebekassebil/teoria).

## Overview

music.js is a music creation library for javascript. It includes functions
and data sets to generate notes, intervals, chords, and scales.

## Example usage

### Note
``` Note.fromLatin(name) ```: Note by latin name and octave

```javascript
var n = Note.fromLatin('A4');  // single note
var freq = n.frequency();  // returns 440
var name = n.latin();  // returns "A"
var octave = n.octave();  // returns 4

var cmaj = Note.fromLatin('C4E4G4');  // chord = array of notes
var freq = cmaj[0].frequency();  // returns 261.625...
var name = cmaj[0].latin();  // returns "C"
var octave = cmaj[0].octave();  // returns 4

var n = Note.fromLatin('C4');  // base note for scale
var majorScale = n.scale('major');  // scale = array of notes
```

### Interval
``` Interval.fromName(name) ```: Interval by name

``` Interval.fromSemitones(num) ```: Interval by semitones

```javascript
var fifth = Interval.fromName('fifth');  // define by name
var wholeStep = Interval.fromSemitones(2); // define by # of semitones

var c = Note.fromLatin('C3');

// use intervals to transpose notes
var d = c.add(wholeStep);

// use intervals to define chords
var cmaj = c.add(['unison','major third','fifth']);
```
