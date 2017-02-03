#Pd Sandbox#

##Abstract##

A parliament of patches to help prototyping and audio synthesis written in Pd.

##Details##

Pd is a wonderful audio playground written by Miller Puckette. He is the MSP in the software formally known as MAX/MSP and a Professor of Computer Music at UCSD. The purpose of this Pd patch collection is to give artists, developers, and users the tools they need to achieve project goals.

However, for the moment (2017), Pd is at an interesting crossroads. Support for the community-based Pd-extended is dwindling. But support his original repo, the *vanilla* edition, is increasing. Pd has been slowly converted by Peter Brinkmann into a standalone library with the [libPD](https://github.com/libpd/libpd) project.

Because the original software is written in C, it provides a fast, cross-platform opportunity for a standardized audio routine. Meaning, you could code once and deploy everywhere with reliable results.

I believe PureData or a similar audio synthesis standard will be necessary for future development. Audio is often a forgotten or neglected part of the user experience.

Contemporary development is a multi-modal process coupled with the increased corporate interest in VR, AR, MR, and *interfaceless* interfaces. Repetitive translation between coding languages and libraries is not a viable option. Pd or a similar library can resolve this.

##Usage##

I created most of these patches at UCSD between 2011 and 2015 under the instruction of the [Miller Puckette](http://msp.ucsd.edu/) and [Tom Erbe](http://musicweb.ucsd.edu/~terbe/wordpress/).

They were built to help friends and colleagues and myself resolve relatively simple common issues. MAX is a popular proprietary alternative to Pd. It has a lot of functionality Pd doesn't. Installing externals is a little tedius and not very portable. 

Everything in this repository is written in Pd-vanilla. Just copy the patches and their support directories into your project directory. It's that easy. 

If you're looking for a place to start lerning Pd, I recommend Dr Hernadez's video [tutorials](https://www.youtube.com/playlist?list=PL12DC9A161D8DC5DC). If you're looking for a more technical introduction to electronic music, please read Miller Puckette's [Theory and Techniques of Electronic Music](http://msp.ucsd.edu/techniques.htm).

###Contents###
Here is a list of the general patches and their basic functionality. You could pull the repository and see the *demo.pd* patch. 

####Presets####

Save and recall patch settings.

p
param
saver
prests
presets20

####Midi####

Patches to debug and interpret midi.

qwerty
midi\_debug
midi
getnotes
getbend
getcontrols
guidenote
guidenote~

####Logic####

Bits of logic to relieve stress.

channel
onoff
rotund
switch

####Envelopes####

Envelope generators to help control signals.

trigenv~
trigadsr~
sampenv~
sampadsr~

####Oscillators####

Generators for modulation and synthesis.

wbosc~
wbpwm~
lpwm~
voscillator~
aatri~
aasquare~
aaramp~
aapwm~
aaosc~


####Effects####

Sometimes you just want to make noise.

tuner~
changerate~
changebit~
looper~
delay~
echo~
reverb

####Panning####

Controls for stereo to 7 speaker surround sound.

panner~
ptwospeakers~
pfourspeakers~
pfivespeakers~
psevenspeakers~
pointone~

####Wavebanks####

Wavetables for oscillators.

lbent
lbenttri
llramp
lrramp
lsquare
ltriangle
sine
square
triangle
lramp
rramp
wavebank

####Windows####

Windows for analysis functions

allthrough
gausian
hamming
hanning
nuttal
welch
square
bartlett
blackman
blackman-harris
blackman-nuttal
flat-top

####Conversions####

Conversions to help with physical emulation.

time2bpm
time2bpm~
time2dist
time2dist~
time2samp
time2sapm~
time2freq
time2freq~
freq2time
freq2time~
freq2samp
freq2samp~
freq2midi
freq2midi~
samp2freq
samp2freq~
samp2time
sampe2time~
bpm2time
bpm2time~
dist2time
dist2time~
midi2freq
midi2freq~
hypotenuse2d
hypotenuse2d~
hypotenuse3d
hypotenuse3d~
unitcircle
unitcircle~
unitsphere
unitsphere~
absolute
absolute~

####Notes####

For many effects, there are three versions. -The generic \<effect\>~ contains a \[param\] patch that can store your settings with a \[preset\] or \[saver\] patch. -The g\<effect\>~ has the same function as the generic but with a small gui. -The \<effect\>\_init version contains the basic functionality required of the other two. 

Most of the time, the parameters of the \_init~ versions function at the signal level. So if you'd like to get wild with your modulation, use the \_init~ version.

##License##

Release under the GNU [GPLv3]() Licence
