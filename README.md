FDSoundActivatedRecorder
========================

Start recording when the user speaks. All you have to do is tell us when to start listening. 
Then we wait for an audible noise and start recording. This is mostly useful for user speech
input and the "Start talking now prompt".

<img src="http://i.imgur.com/wgOcYMl.png">

Status:

 * Works for me and this code is carved out from an active existing project.
 * Requires ARC and iOS 5+


```
/*
 * HOW RECORDING WORKS
 *
 * V            Recording
 * O          /-----------\
 * L         /             \Fall
 * U        /Rise           \
 * M       /                 \
 * E  -----                   --------
 *    Listening                Done
 *
 * We start off by listening and saving the audio level every INTERVAL
 * When the level exceeds the moving average of recent levels by a threshold, we record
 * While recording, we average levels and look for a drop of a certain threshold
 * If the level drops, the average will not include them
 * If a certain number of consecutive levels are a drop then we stop recording
 *
 * SEE: Averaging logs http://physics.stackexchange.com/questions/46228/averaging-decibels
 * Our "averages" are time averages of log squared power, an odd definition
 */
```
