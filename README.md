# rand-mp3
Loop random samples of mp3s

A pure java port of [Cutups](https://github.com/martinaustwick/Cutups).

Thought I'd have a go at hacking it out with the javaFX mediaplayer because haven't really done any javaFX or media stuff in java and seemed like an interesting problem. 

It only has a dependency on pure java 8/maven (as javaFX is bundled with jdk8).

Given a folder full of music, it will pick a random mp3 and choose a random part of the file to play. 
It will then loop a random sized sample from a random position inside the track.

  * Pressing `r` then `enter` will start playing another random sample from  the same file.
  * Pressing `f` then `enter` will start playing another random sample from a random file.
  * Typing `quit` (or `q`) then `enter` will then exit the program. 

The main entry point of the program is the `Runner` class

Build executable jar via standard `mvn clean install`.

Usage:

```sh
java -jar rand-mp3.jar <file-path> <longest possible sample in seconds>
```

e.g:

```sh
java -jar target/rand-mp3-0.0.1-SNAPSHOT.jar "/home/alee/Desktop/Cowboy Bebop/" 4
```

Limitations:
 * Doesn't record the resulting sound
 * Only displays how much of the track was skipped after hitting enter
 * Only tested on linux
 * Hacked together / code is a bit crappy

## Sample output:

<pre>

Starting new track, sample length: 7.953 seconds; For track: "The Seatbelts, Cowboy Bebop Blue - 09-Adieu.mp3"

That sample started at 141.0 seconds


######################################
Starting new track, sample length: 1.84 seconds; For track: "The Seatbelts, Cowboy Bebop No Disc - 07-Want It All Back.mp3"

That sample started at 138.0 seconds


######################################
Starting new track, sample length: 3.39 seconds; For track: "The Seatbelts, Cowboy Bebop Boxed Set (CD 03) - 15-WO QUI NON COIN (Short Sad Version).mp3"

That sample started at 94.0 seconds


######################################
Starting new track, sample length: 4.654 seconds; For track: "The Seatbelts, Cowboy Bebop Remixes Music for Freelance - 07-Radio Free Mars Talk 4.mp3"

That sample started at 9.0 seconds


######################################
Starting new track, sample length: 7.879 seconds; For track: "The Seatbelts, Cowboy Bebop - 15-Rain.mp3"
quit
That sample started at 186.0 seconds


######################################
bye!

</pre>
