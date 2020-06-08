# Matrix Code Generator
This is a screen-accurate Matrix code generator built with HTML5 canvas as a fun weekend project.

I'm a big fan of The Matrix and have always wanted a code generator that truly matched the films. So I watched the opening sequence about 100 times, and with screen shots and video reference, built this over a weekend.

Feel free to copy, use in fan films, whatever you want. If you happen to be a VFX artist or set decorator who uses this on the new film, you'd make my dreams come true by giving me a credit.

## Details
### Glyphs
The glyphs were built in illustrator using screenshots from the first film as reference. I took particular care in making sure the glyphs maintained consistent thickness, proportion, and style.

### Streams
The streaming effect actually works in reverse. You're not seeing streams of code over empty space, it's streams of empty space over code. This turned out to be the simplest implementation.

### Glowing
Canvas filters completely kill performance, so the glow is generated by applying a CSS drop-shadow filter to the canvas.

### Pixelation
There is a pixelation overlay to give the code texture. This just a low-opacity linear-gradient that creates a small checkered pattern.

### Performance
The listed settings impact performance negatively:
- Increased highlighted glyphs
- Increased null streams (I know, less code is actually slower...)
- Decreased font size

### Musings
Much of the screen-accurate randomness of the streams and glyphs was incidental. Turns out the way HTML canvas draws lends itself to those details. For example, the highlighted glyphs sometimes have short trails. Totally incidental result of the way the null streams clear things. The way some code pops in and out of existence. Totally incidentals result of tow clearing trails with a gap between them moving at different speeds.

## Settings
This is pretty configurable. You can change the color, font, fonts, glyphs used. The defaults are set to look as Matrixy as possible.
| Setting | Description | Default |
|---------|-------------|---------|
| **NullStreamDensity** | Controls the amount of null streams. | 6 |
| **nullStreamLengthMin** | Minimum block length of null streams. | 2 |
| **nullStreamLengthMax** | Minimum block length of null streams. | 36 |
| **glyphTransitionRandom** | Ranomizes the time and speed at which glyphs change. | true |
| **streamSpeedRandom** | Ranomizes the speed at which streams move. Streams can change speed during life. | true |
| **streamSpeedMin** | Minimum speed of streams. | 5 |
| **streamSpeedMax** | Maximum speed of streams. | 30 |
| **highlightGlyphDensity** | Controls the density of highlighted glyphs | 1 |
| **glyphOpacityMin** | Maximum opacity of glyphs. | 0.5 |
| **glyphOpacityMax** | Maximum opacity of glyphs. | 1 |
| **colors.default** | Color of default glyphs. | rgba(63, 255, 106, 1) |
| **colors.highlight** | Color of highlight glyphs. | rgba(200, 255, 215, 1) |
| **glyphs** | String of glyphs to use. | qwertyuiopasdfghjklzxcvbnm.:"*<>|123457890-_=+QWERTYUIOP  |
| **fontSize** | Font size of glyphs. | 18 |
| **fontFace** | Font face of glyphs. | 'matrix-code' |

## Future Development
I'll probably tinker with this some more, but I have no specific plans. Here's a list of features I'd like to add if I get the time:
- Change direction of stream.
- Adapt to screen resize.
- Brighter highlighted glyphs. (tough to do because of the stream clearing)
- Improve performance.
