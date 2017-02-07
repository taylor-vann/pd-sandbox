#Pd Sandbox#

##Abstract##

A parliament of patches to help prototyping and audio synthesis written in Pd.

##Details##

(This repository is currently unfinished. Patches are and being tested and uploaded. Please be patient. Thank you.)

Pd is a wonderful audio playground written by Miller Puckette, a Professor of Computer Music at UCSD, and the MSP in the software formally known as MAX/MSP. The purpose of this collection is to give artists, developers, and creators the tools they need to achieve project goals.

However, for the moment (2017), Pd is at an interesting crossroads. Support for the community-based edition, Pd-extended, is essentially dead. But support for Puckette's original repo, the *vanilla* edition, is increasing. Over the last few years, Pd has been slowly converted by Peter Brinkmann into a standalone library called [libpd](https://github.com/libpd/libpd).

Because the original software is written in C, it provides a potential opportunity for a fast, cross-platform, standardized audio routine. Meaning, you could code once and deploy everywhere with the same results.

Audio is often a forgotten or neglected but fundamental part of the user experience. I believe PureData or a similar audio synthesis standard will be necessary for future development.

Contemporary development is now a multi-modal process. Coupled with the increased corporate interest in VR, AR, MR, and *interfaceless* interfaces, repetitive translation between coding languages and libraries is not a viable option. Pd or a similar library can resolve this.

Consider this repository my own contribution to the cause. Every patch, because they are written in Pd vanilla, will work in libpd. Some effects use preset saves. If read/write access is denied to libpd (*cough* iOS *cough*), please use their corresponding *init~* versions.

##Usage##

I created most of these patches at UCSD between 2012 and 2014 under the instruction of [Miller Puckette](http://msp.ucsd.edu/), [Tom Erbe](http://musicweb.ucsd.edu/~terbe/wordpress/), and [Peter Otto](http://music.ucsd.edu/b/Peter+Otto).

Pd is a open-source alternative to MAX (also originally written by Puckette). It has a lot of functionality missing in Pd, namely preset saving and logic. It's simply a different and minimal piece of software. However, Pd is more portable and less resource hungry. These patches were built to remedy relatively common issues between friends and colleagues and myself.

If you're looking for a place to learn Pd, I recommend Dr Hernadez's video [tutorials](https://www.youtube.com/playlist?list=PL12DC9A161D8DC5DC). If you're looking for a more technical introduction to electronic music and DSP, read [Theory and Technique of Electronic Music](http://msp.ucsd.edu/techniques.htm) by Miller Puckette.

Many of the audio effects are my from own personal research and algorithms. I hope they prove useful.
 
Everything in this repository is written in the vanilla edition of Pd. Just copy the patches (and their support directories) into your project directory. It's that easy. 
 
###Contents###

Here is a list of the general patches and their basic functionality. You could pull the repository and see the *demo.pd* patch. 

####Presets####

Save and recall patch settings.

\[param\] or \[p\] - store a number or list

\[saver\] - write and recall params to text file

\[prests\] - quickly write and recall 10 stores

\[presets20\] - quickly write and recall 20 stores

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

####Envelopes####

Envelope generators to help control signals.

\[trigenv~\] - envelope triggered by a bang

\[trigadsr~\] - ADSR triggered by a bang

\[sampenv~\] - envelope driven by sample number

\[sampadsr~\] - ADSR driven by sample number

####Oscillators####

Generators for modulation and synthesis.

\[wbosc~\] - wavebank oscillator, requires \[wavebank\]

\[wbpwm~\] - wavebank pulse modulation, requires \[wavebank\]

\[lpwm~\] - linear pulse width modulation

\[voscillator~\] - linear variable oscillator

\[aatri~\] - anti-aliasing triangle oscillator

\[aasquare~\] - anti-aliasing square oscillator

\[aaramp~\] - anti-aliasing ramp wave oscillator

\[aapwm~\] - anti-aliasing pulse width modulation oscillator

\[aaosc~\] - custom harmonics anti-aliasing oscillator


####Effects####

Sometimes you just want to make noise.

\[tuner~\] - a tuner for when you're out of tune

\[changerate~\] - change the samplerate of a signal (0 - nyquist)

\[changebit~\] - change the bit rate of a signal (2 - 24)

\[looper~\] - a real, fucntional, live looper

\[delay~\] - delay effect

\[echo~\] - echo effect

\[reverb\] - a quality reverb (small - infinite)

####Panning####

Controls for stereo to 7 speaker surround sound.

\[panner~\] - simple panning between two signal outlets

\[ptwospeakers~\] - polar panner between two speakers

\[pfourspeakers~\] - polar panner between four speaker surround sound

\[pfivespeakers~\] - polar panner between five speaker surround sound

\[psevenspeakers~\] - polar panner between seven speaker surround sound

\[pointone~\] - low pass filter for bass emphasis and subwoofers

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

\[allthrough\] - passes analysis unphased, all values 1

\[gaussian\] - gaussian window

\[hanning\] - hanning window

\[hamming\] - hamming window

\[nuttal\] - nuttal window

\[welch\] - welch window

\[square\] - sqaure window (good for eliminatin nyquist in analysis)

\[bartlett\] - bartlet window

\[blackman\] - blackman window

\[blackman-harris\] - blackman-harris window

\[blackman-nuttal\] - blackman-nuttal

\[flat-top\] - flat-top window

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

####Notes####

For many effects, there are three versions. 

-The generic \<effect\>~ contains a \[param\] patch that stores your settings with a \[preset\] or \[saver\] patch. 

-The g\<effect\>~ has the same function as the generic but with a small gui. 

-The \<effect\>\_init version contains the basic functionality required of the other two. 

Most \_init~ versions function at the signal level. So if you'd like to get wild with your modulation, use the \_init~ version.

##License##

Released for students, artists, and instructors under the GNU [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html) Licence.
