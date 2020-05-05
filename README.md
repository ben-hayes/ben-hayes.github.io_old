# Catecophony

Catecophony is a VST3/AU plugin that performs real-time corpus-based concatenative synthesis. Given some source audio (the _corpus_) which is split into thousands of grains and analysed, it attempts to recreate an incoming audio stream (the _target_) using the corpus grains. The result is pointillist sound shapes that are often chaotic and sometimes lovely.

<img src="https://ben-hayes.github.io/catecophony.png" alt="Catecophony user interface" width="640">


## Downloads 

Catecophony is currently in a very buggy alpha state. Please please please don't load this plugin into any projects that you care about, as it _will_ crash at some point.

That said, I'd love to hear what you think, so please download below (currently only macOS VST3 and AU) and share your experiences/ideas/creations with me. I'd also super appreciate if you could let me know about any bugs at ben@benhayes.net

* [macOS VST3 Download](https://github.com/ben-hayes/catecophony/releases/download/v0.0.1-alpha/VST3.Plugin.macOS.zip)
* [macOS AU Download](https://github.com/ben-hayes/catecophony/releases/download/v0.0.1-alpha/AU.Audio.Unit.Plugin.macOS.zip)

## Instructions

Catecophony is very simple to use. Simply drag and drop some audio (one file or many) onto the dark blue portion of the interface, wait for the plugin to analyse the grains, and then play some audio through the plugin. Try using sustained sounds for pulsating textures, drum sounds for glitchy chaos, instrument stems for bubbly stabs, and full tracks for a lot of sonic intensity.

The controls in the yellow _Output_ panel affect the sound in real time.

**Temperature** introduces a degree of randomness to the grain matching process. Useful at low settings for creating some movement, and at high settings for creating total disorientation.

**Relative Matching** activates a slightly more nuanced approach to finding a path through the corpus. Turn it off for a less refined sound.

**Match Magnitude** attenuates the gain of the output grains to match that of the input grains. Turn this on if you want to follow the shape of the incoming audio, and off if you want to explore entirely new sound shapes.

**LPF Cutoff** simply controls the cutoff frequency of a biquadratic Butterworth low-pass filter.

**Dry / Wet** blends in the original signal.

The controls in the red _Synthesis_ parameters affect the way the corpus is analysed and grains are matched. Changes here will not have any effect until you click the _Analyse Corpus_ button or drag in a new audio file.

**Window Type** determines how the edges of grains are smoothed. The Rectangular option is equivalent to no window — expect lots of clicks. Hann & Hamming are safe bets, and Triangular can introduce some subtle variation to the texture of the sound.

**Grain Size** signifies the size of the grains in terms of audio samples. Bigger grains mean more high level features of the corpus are retained, smaller grains offer more abstract timbral features.

**Hop Size** controls how frequently grains are sampled from both the corpus and input stream, and in combination with the _Grain Size_ determines how much they overlap. A big overlap (large grain size and small hop size) can result in a smoother sound, but it also means your computer will have to do a lot more work, so be careful!

**Features** are the heart of Catecophony. These are numerical descriptions of the corpus and target grains, which are used to match the grains. They are also what determines how grains are projected into the visualisation. I'll update this soon with a list of descriptions, but for now, the default combination, or MFCC paired with RMS are good places to start. Note: F0 (fundamental frequency estimate) takes a lot longer to calculate than other features — only use if your computer is up to the job.

## Video

For a more complete overview of the plugin and how it works, check out this video:

<div style="padding:56.25% 0 0 0;position:relative;"><iframe src="https://player.vimeo.com/video/415074832" style="position:absolute;top:0;left:0;width:100%;height:100%;" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe></div><script src="https://player.vimeo.com/api/player.js"></script>
