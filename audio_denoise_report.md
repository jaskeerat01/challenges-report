# Audio Forensic Noise Analysis Report

## Personal Details

**Name:** Jaskeerat Singh  
**Role:** Student 
**Date of Analysis:** 04 October 2026  
**Software Used:** Audacity  
**Purpose:** Analysis and partial enhancement of an audio recording to identify and reduce background interference while preserving speech intelligibility.

**Input File:** `war_intercept.wav`  
**Audio Format:** `WAV`  
**Duration:** `4 minutes 39 seconds`  
**Sample Rate:** `16000 Hz`  
**Channel:** `Stereo`

---

# Executive Summary

The supplied audio recording was examined using waveform and spectrogram analysis to identify background interference affecting speech intelligibility.

The analysis identified several distinct forms of interference:

1. **Stationary tonal components**, visible as horizontal spectral lines at approximately 60 Hz, 703 Hz, 1403 Hz, 2600 Hz, 2801 Hz, and 4202 Hz.
2. **Recurring vertical spectral structures**, occurring approximately nine times per second. These events appear broadband and are particularly prominent above 1 kHz, while residual energy is also present below 1 kHz and continues underneath the speech.
3. **A large curved/spike-shaped frequency-varying component**, observed over an approximately 1.5-second interval and spanning approximately 200 Hz to 4.5 kHz.

Targeted notch filtering was used to reduce the identified stationary tonal components. Comparative low-pass filtering was also performed to determine the frequency region in which speech remains intelligible. A low-pass cutoff around 1000 Hz  produced noticeably clearer speech.

The **vertical interference and large spike-shaped component have not been removed at this stage**. They remain under investigation because their spectral energy overlaps the speech signal. Removing them aggressively using broad frequency filtering could also remove or distort speech information.

Therefore, the current result should be considered a **partial enhancement and characterization of the recording**, rather than a final noise-removal result.

---

# Tools Used

### Audacity

Audacity was used for:

- Waveform inspection
- Spectrogram analysis
- Frequency identification
- Notch filtering
- Low-pass filtering
- Click Removal testing
- Comparative listening
- Evaluation of speech intelligibility

### Analysis techniques used

**Spectrogram analysis:** Used to identify frequency-dependent interference and distinguish stationary tones from changing/repeating components.

**Notch filtering:** Used for narrow, stationary tonal components.

**Low-pass filtering:** Used primarily as a diagnostic method to determine how much of the speech remains intelligible in lower-frequency regions.

**Click Removal:** Tested against the recurring vertical structures. No significant improvement was observed, so the vertical interference was not classified as conventional isolated clicks.

# Methodology

## Analysis

The recording was initially examined through both waveform and spectrogram views.

The spectrogram revealed several different interference patterns. These were separated into three major categories:

### A. Stationary horizontal tones

Several horizontal spectral lines remained relatively constant over time. Approximate frequencies identified during analysis were:

| Component | Approx. Frequency |
| --------- | ----------------: |
| Tone 1    |            ~70 Hz |
| Tone 2    |           ~703 Hz |
| Tone 3    |          ~1403 Hz |
| Tone 4    |          ~2600 Hz |
| Tone 5    |          ~2801 Hz |
| Tone 6    |          ~4202 Hz |

Because these components are relatively stationary in frequency, narrow notch filters were considered appropriate.

### B. Recurring vertical structures

The vertical structures are strongest in approximately the **1–2.5 kHz region**, but spectral energy also extends below 1 kHz.

Most importantly, the vertical interference continues **underneath the conversation**, meaning it cannot simply be removed by selecting periods of silence.

### C. Curved / spike-shaped component

A large curved or diagonal spectral structure was identified.

Observed characteristics:

- Approximate duration: **1.5 seconds**
- Approximate frequency range: **200 Hz–4.5 kHz**
- Frequency changes continuously with time
- Multiple related curved structures may be present

This component does not behave like a single fixed-frequency tone and therefore is not suitable for complete removal using one notch filter.

---

# Finding

The audio contains multiple overlapping interference sources rather than one simple background-noise source.

The most significant findings are:

### Finding 1: Stationary tones

Several fixed-frequency tones were identified and successfully targeted using narrow notch filters.

The tone around approximately **4202 Hz** showed a particularly strong response to notch filtering, with the visible spectral line substantially reduced.

The approximately **703 Hz** component was also attenuated and produced a noticeable improvement in perceived clarity.
### Finding 2: Speech frequency range

A low-pass filter test showed that the conversation remained reasonably understandable when frequencies above approximately **800 Hz** were attenuated.

Further testing indicated that useful speech content extends to around **1 kHz**, so the final speech signal should not be treated as being limited strictly to frequencies below 800 Hz.

![[Pasted image 20261004022054.png]]

### Finding 3: Vertical interference

The recurring vertical structures were not successfully removed using Click Removal.

Their characteristics suggest a repetitive broadband interference component rather than isolated random clicks.

Because this interference extends into the speech-frequency region, aggressive filtering could damage the conversation.

![[Pasted image 20261004022214.png]]
### Finding 4: Spike-shaped interference

The large spike/curved component remains present.

It spans a very broad frequency range and changes frequency over time. Since it overlaps the speech signal, simple frequency deletion would cause significant speech loss.

**This component has not been completely removed but significantly reduced with previous click removal filter**

---

# Outcome

The analysis produced a **partially enhanced working version** of the recording.

### Successfully addressed

- Several stationary tonal components were identified and attenuated.
- The ~4202 Hz tone was substantially reduced.
- The ~703 Hz tone was attenuated and produced some improvement in clarity.
- Low-pass testing established that much of the useful speech remains in the lower-frequency region.

### Not yet removed

- **Recurring vertical interference:** remains audible and spectrally visible.
- **Large spike/curved interference:** remains present and has not been removed.

The remaining interference requires more targeted processing because both components overlap the speech signal.

---

# Step-by-Step Process

## Step 1: Spectrogram Examination

The original recording was loaded into Audacity and viewed in Spectrogram mode.

The spectrogram showed horizontal tones, vertical repeating structures, and large curved frequency-varying components.

---

## Step 2: Identification of Stationary Tones

Several horizontal spectral lines were identified at approximately:

- 72 Hz
- 703 Hz
- 1403 Hz
- 2600 Hz
- 2801 Hz
- 4202 Hz

These were treated as stationary tonal interference.

![[Pasted image 20261004022504.png]]

---

## Step 3: Notch Filtering

Narrow notch filters were applied individually to the identified stationary frequencies.

A Q factor of approximately 14 was initially used to keep the attenuation relatively narrow.

The approximately 2800 Hz component showed a strong reduction after processing and the similar process was performed for all other found frequencies.

![[Pasted image 20261004021958.png]]

---

## Step 4: Speech-Frequency Investigation

A low-pass filter was used as a diagnostic test.

An initial cutoff of approximately **800 Hz** was tested.

The conversation remained reasonably audible and became clearer in comparison with the unfiltered recording.

A further test around **1 kHz** was performed because some speech information was audible above 800 Hz.

![[Pasted image 20261004022756.png]]

---

## Step 5: Identification of Vertical Interference

The spectrogram was examined at higher temporal resolution.

Approximately **nine recurring vertical structures per second** were observed.

![[Pasted image 20261004022853.png]]

The structures are strongest in approximately the **1–2.5 kHz** region but are also present below 1 kHz.

The interference continues during speech rather than disappearing when speech is present.

---

## Step 6: Click Removal Test

Audacity's Click Removal was tested against the vertical structures.

The processing produced **no significant audible or visible improvement**.
### Result

> No significant improvement was observed. The vertical structures were therefore not treated as ordinary isolated clicks.

---

## Step 7: Detailed Examination of the Vertical Interference

A higher-resolution spectrogram was examined to determine the frequency characteristics of the recurring interference.

The interference was observed to continue underneath the speech and therefore could not safely be removed by simply deleting the affected frequency regions.

---

## Step 8: Identification of the Spike-Shaped Component

A large curved/diagonal spectral component was identified.

Measured characteristics:

**Duration:** ~1.5 seconds  
**Frequency span:** ~200 Hz–4.5 kHz

![[Pasted image 20261004023337.png]]


This component was not processed further at this stage because it overlaps a substantial portion of the speech spectrum.

---

# Final Assessment

The recording contains **multiple overlapping interference mechanisms**.

The stationary tones can be treated effectively using narrow frequency-domain attenuation, and this processing has already improved the recording to some extent.

However, the two more complex components remain unresolved but the conversation can be understood and transcribed

---

# Processing Log

| Step | Operation               | Setting              | Purpose                     |
| ---- | ----------------------- | -------------------- | --------------------------- |
| 1    | Notch                   | ~4202 Hz             | Remove stationary tone      |
| 2    | Notch                   | ~2801 Hz             | Remove stationary tone      |
| 3    | Notch                   | ~2600 Hz             | Remove stationary tone      |
| 4    | Notch                   | ~1403 Hz             | Remove stationary tone      |
| 5    | Notch                   | ~703 Hz              | Remove low-frequency tone   |
| 6    | Notch                   | ~70 Hz               | Remove stationary tone      |
| 7    | Low-pass                | 800 Hz               | Diagnostic speech isolation |
| 8    | Low-pass                | 1 kHz                | Diagnostic comparison       |
| 9    | Curved component        | ~1.5 s, ~200–4500 Hz | Characterization            |
| 10   | Vertical-event analysis | ~9/sec               | Characterization            |
| 11   | Click Removal           | -                    | Vertical-event removal      |

# Audio Transcription:

England
December 30th, 1942

Dear Mother and Dad

Though I'm not supposed to tell you where I've been, I think even the hardest of censors would let a guy tell about Christmas Day as I enjoyed it over here.

I have to start with Christmas Eve. It was when I opened your various Christmas parcels. Some of the fellows, the rats, were standing around helping and grabbing.

Hey, lay off, you guys! They're my cookies!
Oh, I like chocolate!
Hey, Charlie, your mother's a swell cook!
Hey, open this one, Charlie. It's small, but heavy.

Hey, will you look at that! That's what I've been yelling for!
What is it?
Oh, it's a pocket whetstone.
Isn't that swell? My father sent me that. Now I don't care whether I can get new razor blades or not.
You'd better hang on to that, brother, or I'll be swiping it.
You can have anything but my whetstone. I'm going to hang on to this.
Come in.
Captain Bagley, sir, note from headquarters.
Headquarters? What have I been doing now? Special dispatch letter.

Hey, guys! I'm going to have dinner with the Queen!
Huh? He's been out in the sun too long.
That's what the note says! Lieutenant Sam Brush and me too? 
Yeah.
and I have been chosen as the two American officers to have Christmas dinner with Queen Mary!
Wow!

It wasn't kidding, Mother and Dad; we really were invited. You know, Mother, you've always told me it was nice to take along some little thing for your hostess. Well, thanks to your Christmas presents, I was able to put together a small package for the Queen. I admit I hesitated some time over what to put in, and it was hardly a royal-looking parcel: a box labeled Perfection Paper Clips, Six Gross, but I somehow thought the Queen wouldn't mind.

Well, when we got there...

Your Majesty: Captain Charles Bagley, Lieutenant Sam Brush.
How do you do, Captain Bagley, Lieutenant Brush? I'm very glad to see you.
How do you do?
It was very nice of you to come.
It's nice of you to ask us.
Charlie...
I think Christmas is the time when we all want to be with our own families, but if we can't, well, the next best thing is to be with someone else's, don't you think?
Yes.
My family is broken up by the war, too, you know.
Oh, yes.
Yes, I guess that's so.
Now, this being Christmas, will you accept a little gift from me, Captain Bagley? Here's one for you, and one for you, Lieutenant Brush.
Thank you, Your Majesty.
And now, there... I see you have a parcel, too. Is that by any chance for me?
Yes, it is, Your Majesty. You'll laugh, I guess. It isn't really paper clips, but that's the only box I had.
Oh, what fun! Let's all open our presents together, shall we?

Cigarettes!
A box of Chesterfield cigarettes!
I got a silver penknife and a pencil! Oh, will I hang on to these!
Oh, thank you, Captain Bagley. You know how we long for paper clips over here? And so few, isn't it? But tell me, what's this this is in?
Oh, it's a whetstone: to sharpen knives and razor blades and things. I thought that maybe down in the kitchen, or maybe the King had a razor...
Oh, he could! It's the very thing we need. Now, I know these things were in your Christmas boxes from home, and I think it's very generous of you to share them with me. Now, will you join the other guests and go in to dinner? Captain Bagley, you are to sit on my left. I would like to hear about America, and your family, and all the things you do at home.

When Lieutenant Brush and I left at midnight, it was as if we'd spent an evening with old friends. It was grand.

Must close now. Hope you're all well.

Love,
Charlie
