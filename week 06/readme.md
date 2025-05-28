# Week 6 Tasks

- Explored sound and its physical properties
- Explored sound synthesis by creating an oscillator
- Explored filters and frequency modulation 


**Requirements:**

- Written in Processing 4.3
- Run 'sci fi sound' file in Processing


**Sci-fi Sound Weekly Task**

Aim: Using at least 3 oscillators and/or filters, design a sound for a sci-fi movie when the main characters arrive onto a new planet


- Started by building upon example code given in class
- Added 'soundPlayed' so the sound plays only once
- set volume and frequency: 
```sine1.amp(0.5);' and 'sine1.freq(220);'  (A3 note)
    if (elapsed < 1500) {
    float freq = 220 + 200 * sin(radians(elapsed * 0.3));
    float amp = map(elapsed, 0, 1500, 0.5, 0);
    
    sine1.freq(freq);
    sine1.amp(amp);
```
- Used a frequency modulator so the sound goes up and down at around 220Hz to make a 'wavy' sound 
- Volume will fade out gradually from 0.5 to 0
- Decided to add in more oscillators and filters to make the sound more interesting 
- 'TriOsc' using a triangle wave oscillator to add harmonics
- Also added 'LowPass' filter to control high-frequency

- Added: 
```
  sineOsc.amp(0.0);
  triOsc.amp(0.0);
  sineOsc.freq(220);
  triOsc.freq(220);
```

- Routed both oscillators through the LowPass filter
- Set sound duration to 7 seconds

- Frequency modulation: 
```
    float baseFreq = map(elapsed, 0, duration, 220, 660);
    float vibrato = 15 * sin(radians(elapsed * 2));
    float freq = baseFreq + vibrato;
```   

- vibrato to add pitch fluctation
- Set the triangle oscillator 1 octave lower to add harmony and made it quieter 

- Low-pass filter's cutoff frequency is from 200Hz (muffled) to 5000Hz (brighter)
