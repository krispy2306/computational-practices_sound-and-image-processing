# Week 7 Tasks
- Explored the modulo operator to create sound patterns
- Explored what algorithmic music is and examples
- Explored loading sound samples
- Created simple drum patterns using class knowledge  


**Requirements:**
Written in Processing 4.3
Run 'pixels' and 'gradient' file in Processing


**Sample Loop Weekly Task**
Aim: Using at least 4 samples, create a drum pattern.

- Went online to download sample sound files
- Wanted to create a techno sounding loop so downloaded a 'trance kick' for bass and a 'breakcore' lead file. (Check data file for sample files. ALL FILES DOWNLOADED FOR FREE FROM https://freesound.org/)


- Loaded the sample files and set the bpm to 120 beats per minute (this took a lot of tweaking to get the sounds to align!)
- Set the kick's (sample 1) amp to (0.6) and the rate to (0.5*2) - wanted it to be quieter than the lead. I also wanted the kick to play every half beat.
- Set the breakcore lead's (sample 2) amp to (1.0 * 2) and the rate to (1.0 * 1.2) - wanted a louder lead 
- Set the vocal sample (sample 3) to (0.1 * 2) and the rate to (0.5 * 2) - wanted the vocal to be quieter 

- Added function to play sample 2 inside the setup loop as I was altering the rate and volume

```java
if (frameCount % 8 == 0) {
    sample3.play();
    sample3.loop();
}
```

- added so that the vocal sample comes in on the 8th beat

- Background also changes between random() RGB values every beat
- Loops indefinitely