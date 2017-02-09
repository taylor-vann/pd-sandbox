#Pd Sandbox#

##Abstract##

A parliament of Pd patches for prototyping and audio synthesis.

##Details##

(This repository is currently unfinished. Patches are and being tested and uploaded. Please be patient. Thank you.)

The purpose of this collection is to give artists, developers, and creators the tools they need to achieve project goals without getting deep in the dirt with the acoustics behind the effects required.

However, Pd is at an interesting crossroads. Support for the community-based edition, Pd-extended, is essentially dead. But Puckette's original repo, the *vanilla* edition, is gaining support. 

Because the original software is written in C, there is a potential opportunity for a fast, cross-platform, standardized audio routine. Meaning, you could code once and deploy everywhere with the same results. Consequentially, over the last few years Pd has been slowly converted by Peter Brinkmann into the stand-alone library [libpd](https://github.com/libpd/libpd).

Contemporary development is now a multi-modal process. Audio is often a forgotten or neglected but fundamental part of the user experience. Coupled with the increased corporate interest in VR, AR, MR, and interface-less interfaces, repetitive translation between coding languages and libraries is not a viable option. I believe PureData or a similar audio synthesis standard will be necessary for consistent development.

Consider this repository my own small contribution to the cause. Every patch, because they are written in Pd vanilla, will work in libpd. Some effects use preset saves. If read/write access is denied to libpd (\*cough\* iOS \*cough\*), please use their corresponding \<effect\_\>*init~* versions and refrain from using the \[p\], \[param\], \[saver\], \[presets\], or \[presets20\] patches.

If you're interested in custom audio effects or if there is anything missing in in this collection, please don't hesitate to contact me.

##Usage##

I created most of these patches at UCSD between 2012 and 2014 under the instruction of [Miller Puckette](http://msp.ucsd.edu/), [Tom Erbe](http://musicweb.ucsd.edu/~terbe/wordpress/), and [Peter Otto](http://music.ucsd.edu/b/Peter+Otto). I'm currently revising and updating them (2017).

Pd is a open-source alternative to MAX (both originally written by Puckette). Ithas some expected functionality missing in Pd, namely preset saving and logic. Pd is simply a different piece of software. However, Pd is more portable and less resource hungry. These patches were built to remedy shared issues and frustrations between friends, colleagues, and myself.

If you're looking for a place to learn the basics of Pd, I recommend Dr Hernadez's [video tutorials](https://www.youtube.com/playlist?list=PL12DC9A161D8DC5DC) or Johannes Kreidler's [loadbang tutorials](http://www.pd-tutorial.com/). If you're looking for a more technical introduction to electronic music and DSP, read Theory and Technique of [Electronic Music](http://msp.ucsd.edu/techniques.htm) by Miller Puckette.

Everything in this repository is written in the vanilla edition of Pd. Just copy the patches (and their support directories) into your project directory. It's that easy. 
 
###Contents###

These patches provide common audio effects, preset saves, midi control, anti-aliasing oscillators, sample manipulation, fun noisy aliasing oscillators, surround-sound panning, conversions between audio units (samples, time, frequency, distance), ADSRs, wavetables, and windows for analysis.

Here is a list of the general patches and their basic functionality. You could also pull the repository and open the *demo.pd* patch. 

####Midi####

Patches to debug and interpret midi.

\[qwerty\] - a midi keyboard for your keyboard

\[midi\_debug\] - print all midi input

\[midi\] - required for getnotes, getbend, and getcontrols (only use once)

\[getnotes\] - get notes from midi channel (default 1), requires \[midi\]

\[getbend\] - get bend from midi channel (default 1), requires \[midi\]

\[getcontrols\] - get controls from midi channel (default 1), requires \[midi\]

\[guidenote\] or \[guidenote~\]- curate midi input and signals to set scales

####Logic####

Bits of logic to relieve stress.

\[onoff\] - zero/non-zero input triggers two contrasting zero/non-zero outputs

\[switch\] - increment between a range of integers

\[rotund\] - increment between a range of integers and back around again

\[channel\] - zero/non-zero input directs output between two outputs

####Presets####

Save and recall patch settings.

\[param\] or \[p\] - store a number or list

\[saver\] - write and recall params to text file

\[presets\] - quickly write and recall 10 stores

\[presets20\] - quickly write and recall 20 stores

####Conversions####

Conversions to help with physical emulation.

\[time2bpm\] or \[time2bpm~\] - convert mS to bpm

\[time2dist\] or \[time2dist~\] - convert mS to meters

\[time2samp\] or \[time2sapm~\] - convert mS to number of sample length

\[time2freq\] or \[time2freq~\] - convert mS to frequency

\[freq2time\] or \[freq2time~\] - convert frequency to mS

\[freq2samp\] or \[freq2samp~\] - convert frequency to sample length

\[freq2midi\] or \[freq2midi~\] - convert frequency to midi

\[midi2freq\] or [midi2freq~\] - convert midi to frequency

\[samp2freq\] or \[samp2freq~\] - convert sample length to frequency

\[samp2time\] or \[sampe2time~\] - convert sample length to mS

\[bpm2time\] or \[bpm2time~\] - convert bpm to mS

\[dist2time\] or \[dist2time~\] - convert meters to mS

\[hypotenuse2d\] or \[hypotenuse2d~\] - calculate 2d hypotenuse

\[hypotenuse3d\] or \[hypotenuse3d~\] - calulate 3d hypotenuse

\[unitcircle\] or \[unitcircle~\] - calculate point on the unit circle

\[unitsphere\] or \[unitsphere~\] - calculate point on the unit sphere

\[absolute\] or \[absolute~\] - calculate absolute value (unnecessary)

####Table Lookups####

Wavetables for oscillators.

\[lbent\] - linear bent triangle table

\[llramp\] - linear left-leaning ramp table

\[lrramp\] - linear right-leaning ramp table

\[lsquare\] - linear square table

\[ltriangle\] - linear triangle table

\[sine\] - sine wave

\[square\] - square wave sinusoid table

\[triangle\] - triangle wave sinusoid table

\[lramp\] - left-leaning ramp sinusoid table

\[rramp\] - right-leaning ramp sinusoid table

\[wavebank\] - object containing all tables listed above

####Windows####

Windows for analysis functions

\[allthrough\] - unphased analysis, all table values are 1

\[hanning\] - hanning window

\[hamming\] - hamming window

\[gaussian\] - gaussian window

\[nuttal\] - nuttal window

\[welch\] - welch window

\[bartlett\] - bartlet window

\[blackman\] - blackman window

\[blackman-harris\] - blackman-harris window

\[blackman-nuttal\] - blackman-nuttal

\[flat-top\] - flat-top window

\[square\] - sqaure window (eliminate nyquist in analysis)

####Generators####

Generators for modulation and synthesis.

\[wbosc~\] - wavebank oscillator, requires \[wavebank\]

\[wbpwm~\] - wavebank pulse modulation, requires \[wavebank\]

\[lpwm~\] - linear pulse width modulation

\[voscillator~\] - linear variable oscillator

\[aatri~\] - anti-aliasing triangle oscillator

\[aasquare~\] - anti-aliasing square oscillator

\[aaramp~\] - anti-aliasing ramp wave oscillator

\[aapwm~\] - anti-aliasing pulse width modulation oscillator

\[aaosc~\] - anti-aliasing oscillator for up to 10 custom harmonics

####Samples####

Objects to help with sample manipulation

\[sampleplay~\] - play a file from disk

\[sampleload~\] - load a sample to a table (required for most sample objects)

\[scratch\] or \[scratch~\] - swipe through a sample

\[trigplay~\] - play a sample from one position to the other with a bang

\[tapeplay~\] - play a sample from one position to the other by sample number

\[trigggrain~\] - time-stretch and pitch-shift independently with a bang

\[tapegrain~\] - time-stretch and pitch-shift independently by sample number

\[sampletable~\] - write a signal to a table

\[samplesave~\] - write a signal to disk

####Envelopes####

Envelope generators to help control signals.

\[trigenv~\] - envelope triggered by a bang

\[trigadsr~\] - ADSR triggered by a bang

\[sampenv~\] - envelope driven by sample number

\[sampadsr~\] - ADSR driven by sample number

####Effects####

Sometimes you just want to make noise.

\[changerate~\] - change the samplerate of a signal (0 - nyquist)

\[changebit~\] - change the bit rate of a signal (2 - 24)

\[gate~\] - gate a signal

\[limiter~\] - attenuate amplitude when signals pass certain threshold

\[compressar~\] - squeeze the dynamic range of a signal

\[expander~\] - increase amplitude when signals are below a threshold

\[delay~\] - delay a signal

\[echo~\] - create an echo

\[reverb~\] - an infinite reverb

\[tremolo~\] - modulate amplitude with a variable oscillator

\[leslie~\] - rotating speaker emulation

\[flanger~\] - modulated delay with feedback

\[chorus~\] - filtered modulated delay with feedback 

####Panning####

Controls for stereo and surround sound.

\[panner~\] - simple panning between two signal outlets

\[ptwospeakers~\] - polar panner between two speakers

\[pfourspeakers~\] - polar panner between four speaker surround-sound

\[pfivespeakers~\] - polar panner between five speaker surround-sound

\[psevenspeakers~\] - polar panner between seven speaker surround-sound

\[pointone~\] - low pass filter for bass emphasis and subwoofers

####Tools####

\[tuner~\] - a tuner for when you're out of tune

\[looper~\] - a real, fucntional, live looper

####Notes####

For many effects, there are three versions. 

-The generic \<effect\>~ contains a \[param\] patch that stores your settings in conjunction with a \[preset\] or \[saver\] patch. 

-The g\<effect\>~ has the same function as the generic but with a small gui. 

-The \<effect\>\_init version contains the basic functionality required of the other two. 

Most \_init~ versions function at the signal level. So if you'd like to get wild with your modulation, use the \_init~ version.

##License##

Released for students, artists, and instructors under the GNU [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html) Licence.
