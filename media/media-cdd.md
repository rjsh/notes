<a id="s5"></a>
# 5. Multimedia Compatibility

Device implementations *MUST* include at least one form of audio output, such as speakers, headphone jack, external speaker
connection, etc.


## 5.1. Media Codecs

Device implementations *MUST* support the core media formats specified in the Android SDK documentation \[[Resources, 58](http://developer.android.com/guide/appendix/media-formats.html)\] except
where explicitly permitted in this document. Specifically, device implementations *MUST* support the media formats, encoders,
decoders, file types and container formats defined in the tables below. All of these codecs are provided as software
implementations in the preferred Android implementation from the Android Open Source Project.

**Please note that neither Google nor the Open Handset Alliance make any representation that these codecs are unencumbered by third-party patents. Those intending to use this source code in hardware or software products are advised that implementations of this code, including in open source software or shareware, may require patent licenses from the relevant patent holders.**

Note that these tables do not list specific bitrate requirements for most video codecs because current device hardware does not
necessarily support bitrates that map exactly to the required bitrates specified by the relevant standards. Instead, device
implementations *SHOULD* support the highest bitrate practical on the hardware, up to the limits defined by the specifications.

<style contenteditable="">
table,tr,td,th      { border: 1px solid black ; border-collapse: collapse}
</style>

<table>
<tr>
<th>Type</th>
<th>Format / Codec</th>
<th>Encoder</th>
<th>Decoder</th>
<th>Details</th>
<th>File Type(s) / Container Formats</th>
</tr>
<tr>
<td rowspan="11">Audio</td>
<td>MPEG-4 AAC Profile (AAC LC)</td>
<td>REQUIRED for device implementations that include microphone
hardware and define android.hardware.microphone.</td>
<td>REQUIRED</td>
<td>Support for mono/stereo/5.0/5.1* content with standard sampling
rates from 8 to 48 kHz.</td>
<td rowspan="4">
<ul>
<li>3GPP (.3gp)</li>
<li>MPEG-4 (.mp4, .m4a)</li>
<li>ADTS raw AAC (.aac, decode in Android 3.1+, encode in
Android 4.0+, ADIF not supported)</li>
<li>MPEG-TS (.ts, not seekable, Android 3.0+)</li>
</ul>
</td>
</tr>
<tr>
<td>MPEG-4 HE AAC Profile (AAC+)</td>
<td>REQUIRED for device implementations that include microphone
hardware and define android.hardware.microphone.</td>
<td>REQUIRED</td>
<td>Support for mono/stereo/5.0/5.1* content with standard sampling
rates from 16 to 48 kHz.</td>
</tr>
<tr>
<td>MPEG-4 HE AAC v2 Profile (enhanced AAC+)</td>
<td></td>
<td>REQUIRED</td>
<td>Support for mono/stereo/5.0/5.1* content with standard sampling
rates from 16 to 48 kHz.</td>
</tr>
<tr>
<td>MPEG-4 Audio Object Type ER AAC ELD (Enhanced Low Delay
AAC)</td>
<td>REQUIRED for device implementations that include microphone
hardware and define android.hardware.microphone.</td>
<td>REQUIRED</td>
<td>Support for mono/stereo content with standard sampling rates
from 16 to 48 kHz.</td>
</tr>
<tr>
<td>AMR-NB</td>
<td>REQUIRED for device implementations that include microphone
hardware and define android.hardware.microphone.</td>
<td>REQUIRED</td>
<td>4.75 to 12.2 kbps sampled @ 8kHz</td>
<td>3GPP (.3gp)</td>
</tr>
<tr>
<td>AMR-WB</td>
<td>REQUIRED for device implementations that include microphone
hardware and define android.hardware.microphone.</td>
<td>REQUIRED</td>
<td>9 rates from 6.60 kbit/s to 23.85 kbit/s sampled @ 16kHz</td>
<td>3GPP (.3gp)</td>
</tr>
<tr>
<td>FLAC</td>
<td></td>
<td>REQUIRED (Android 3.1+)</td>
<td>Mono/Stereo (no multichannel). Sample rates up to 48 kHz (but
up to 44.1 kHz is recommended on devices with 44.1 kHz output, as
the 48 to 44.1 kHz downsampler does not include a low-pass filter).
16-bit recommended; no dither applied for 24-bit.</td>
<td>FLAC (.flac) only</td>
</tr>
<tr>
<td>MP3</td>
<td></td>
<td>REQUIRED</td>
<td>Mono/Stereo 8-320Kbps constant (CBR) or variable bit- rate
(VBR)</td>
<td>MP3 (.mp3)</td>
</tr>
<tr>
<td>MIDI</td>
<td></td>
<td>REQUIRED</td>
<td>MIDI Type 0 and 1. DLS Version 1 and 2. XMF and Mobile XMF.
Support for ringtone formats RTTTL/RTX, OTA, and iMelody</td>
<td>
<ul>
<li>Type 0 and 1 (.mid, .xmf, .mxmf)</li>
<li>RTTTL/RTX (.rtttl, .rtx)</li>
<li>OTA (.ota)</li>
<li>iMelody (.imy)</li>
</ul>
</td>
</tr>
<tr>
<td>Vorbis</td>
<td></td>
<td>REQUIRED</td>
<td></td>
<td>
<ul>
<li>Ogg (.ogg)</li>
<li>Matroska (.mkv)</li>
</ul>
</td>
</tr>
<tr>
<td>PCM/WAVE</td>
<td>REQUIRED</td>
<td>REQUIRED</td>
<td>8-bit and 16-bit linear PCM** (rates up to limit of
hardware).Devices MUST support sampling rates for raw PCM recording
at 8000,16000 and 44100 Hz frequencies</td>
<td>WAVE (.wav)</td>
</tr>
<tr>
<td rowspan="5">Image</td>
<td>JPEG</td>
<td>REQUIRED</td>
<td>REQUIRED</td>
<td>Base+progressive</td>
<td>JPEG (.jpg)</td>
</tr>
<tr>
<td>GIF</td>
<td></td>
<td>REQUIRED</td>
<td></td>
<td>GIF (.gif)</td>
</tr>
<tr>
<td>PNG</td>
<td>REQUIRED</td>
<td>REQUIRED</td>
<td></td>
<td>PNG (.png)</td>
</tr>
<tr>
<td>BMP</td>
<td></td>
<td>REQUIRED</td>
<td></td>
<td>BMP (.bmp)</td>
</tr>
<tr>
<td>WEBP</td>
<td>REQUIRED</td>
<td>REQUIRED</td>
<td></td>
<td>WebP (.webp)</td>
</tr>
<tr>
<td rowspan="5">Video</td>
<td>H.263</td>
<td>REQUIRED for device implementations that include camera
hardware and define android.hardware.cameraor
android.hardware.camera.front.</td>
<td>REQUIRED</td>
<td></td>
<td>
<ul>
<li>3GPP (.3gp)</li>
<li>MPEG-4 (.mp4)</li>
</ul>
</td>
</tr>
<tr>
<td>H.264 AVC</td>
<td>REQUIRED for device implementations that include camera
hardware and define android.hardware.cameraor
android.hardware.camera.front.</td>
<td>REQUIRED</td>
<td>Baseline Profile (BP)</td>
<td>
<ul>
<li>3GPP (.3gp)</li>
<li>MPEG-4 (.mp4)</li>
<li>MPEG-TS (.ts, AAC audio only, not seekable, Android
3.0+)</li>
</ul>
</td>
</tr>
<tr>
<td>MPEG-4 SP</td>
<td></td>
<td>REQUIRED</td>
<td></td>
<td>3GPP (.3gp)</td>
</tr>
<tr>
<td>VP8****</td>
<td>REQUIRED (Android 4.3+)</td>
<td>REQUIRED (Android 2.3.3+)</td>
<td></td>
<td>WebM (.webm) and Matroska (.mkv, Android 4.0+)***</td>
</tr>
<tr>
<td>VP9</td>
<td></td>
<td>REQUIRED (Android 4.4+)</td>
<td></td>
<td>WebM (.webm) and Matroska (.mkv, Android 4.0+)***</td>
</tr>
</table>

+ \**Note*: Only downmix of 5.0/5.1 content is required; recording or rendering more than 2 channels is optional.
+ \*\**Note*: 16-bit linear PCM capture is mandatory. 8-bit linear PCM capture is not mandatory.
+ \*\*\**Note*: Device implementations *SHOULD* support writing Matroska WebM files.
+ \*\*\*\**Note*: For acceptable quality of web video streaming and video-conference services, device implementations *SHOULD*
  use a hardware VP8 codec that meets the requirements in \[[Resources, 86](http://www.webmproject.org/hardware/rtc-coding-requirements/)\].

## 5.2. Video Encoding

Android device implementations that include a rear-facing camera and declare `android.hardware.camera` *SHOULD* support the
following H.264 video encoding profiles.


 | SD (Low quality) | SD (High quality) | HD (When supported by hardware)
-|------------------|-------------------|--------------------------------
 Video resolution | 176 x 144 px | 480 x 360 px        | 1280 x 720 px
 Video frame rate | 12 fps       | 30 fps              | 30 fps
 Video bitrat     | 56 Kbps      | 500 Kbps or higher  | 2 Mbps or higher
 Audio codec      | AAC-LC       | AAC-LC              | AAC-LC
 Audio channels   | 1 (mono)     | 2 (stereo)          | 2 (stereo)
 Audio bitrate    | 24 Kbps      | 128 Kbps            | 192 Kbps

Android device implementations that include a rear-facing camera and declare `android.hardware.camera` *SHOULD* support the
following VP8 video encoding profiles

 |SD (Low quality) | SD (High quality) | HD 720p (When supported by hardware) | HD 1080p (When supported by hardware)
-|-----------------|-------------------|--------------------------------------|--------------------------------------
 **Video resolution**  | 320 x 180 px | 640 x 360 px | 1280 x 720 px | 1920 x 1080 px 
 **Video frame rate**  | 30 fps       | 30 fps       | 30 fps        | 30 fps 
 **Video bitrate**     | 800 Kbps     | 2 Mbps       | 4 Mbps        | 10 Mbps 


## 5.3. Video Decoding

Android device implementations *SHOULD* support the following VP8, VP9 and H.264 video decoding profiles. Device
implementations *SHOULD* also support dynamic video resolution switching within the same stream for VP8, VP9 and H.264
codecs.

 |SD (Low  quality) | SD (High quality) | HD 720p (When supported by hardware) | HD 1080p (When supported by hardware)
------------------|-------------------|--------------------------------------|--------------------------------------
 **Video resolution **| 320 x 180 px |        640 x 360 px |       1280 x 720 px |                1920 x 1080 px 
 **Video frame rate** | 30 fps       |        30 fps       |       30 fps        |                30 fps 
 **Video bitrate**    | 800 Kbps     |        2 Mbps       |       8 Mbps        |                20 Mbps 

## 5.4. Audio Recording

When an application has used the android.media.AudioRecordAPI to start recording an audio stream, device implementations that
include microphone hardware and declare `android.hardware.microphone` *MUST* sample and record audio with each of these
behaviors:

+  The device *SHOULD* exhibit approximately flat amplitude versus frequency characteristics; specifically, ±3 dB, from 100 Hz to
+  4000 Hz
+  Audio input sensitivity *SHOULD* be set such that a 90 dB sound power level (SPL) source at 1000 Hz yields RMS of 2500 for
+  16-bit samples.
+  PCM amplitude levels *SHOULD* linearly track input SPL changes over at least a 30 dB range from -18 dB to +12 dB re 90 dB
   SPL at the microphone.
+  Total harmonic distortion *SHOULD* be less than 1% for 1Khz at 90 dB SPL input level.

In addition to the above recording specifications, when an application has started recording an audio stream using the
`android.media.MediaRecorder.AudioSource.VOICE_RECOGNITION` audio source:


* Noise reduction processing, if present, *MUST* be disabled.
* Automatic gain control, if present, *MUST* be disabled.

From *Android 4.4*, `android.media.MediaRecorder.AudioSource` class has a new audio source: `REMOTE_SUBMIX`. Devices *MUST* properly implement the `REMOTE_SUBMIX` audio source so that when an application uses the `android.media.`AudioRecord API to record from this audio source, it can capture a mix of all audio streams except for the following:

`STREAM_RING`
`STREAM_ALARM`
`STREAM_NOTIFICATION`

*Note*: while some of the requirements outlined above are stated as "*SHOULD*" since *Android 4.3*, the Compatibility Definition for a future version is planned to change these to "*MUST*". That is, these requirements are optional in *Android 4.4* but will be required by a future version. Existing and new devices that run Android are very strongly encouraged to meet these requirements, or they will not be able to attain Android compatibility when upgraded to the future version.

If the platform supports noise suppression technologies tuned for speech recognition, the effect *MUST* be controllable from the `android.media.audiofx.NoiseSuppressor` API. Moreover, the "`uuid`" field for the noise suppressor's effect descriptor *MUST* uniquely identify each implementation of the noise suppression technology.


## 5.5. Audio Latency

Audio latency is the time delay as an audio signal passes through a system. Many classes of applications rely on short latencies, to achieve real-time sound effects.

For the purposes of this section:

+  "*output latency*" is defined as the interval between when an application writes a frame of PCM-coded data and when the
   corresponding sound can be heard by an external listener or observed by a transducer
+  "*cold output latency*" is defined as the output latency for the first frame, when the audio output system has been idle and
   powered down prior to the request
+  "*continuous output latency*" is defined as the output latency for subsequent frames, after the device is already playing audio
+  "input latency" is the interval between when an external sound is presented to the device and when an application reads the
   corresponding frame of PCM-coded data
+  "*cold input latency*" is defined as the sum of lost input time and the input latency for the first frame, when the audio input
   system has been idle and powered down prior to the request
+  "*continuous input latency*" is defined as the input latency for subsequent frames, while the device is already capturing audio
+  "*OpenSL ES PCM buffer queue API*" is the set of PCM-related *OpenSL ES* APIs within *Android NDK*; see
   *`NDK_root`*`/docs/opensles/index.html`

Per [Section 5](#s5), all compatible device implementations *MUST* include at least one form of audio output. Device implementations
*SHOULD* meet or exceed these output latency requirements:

* cold output latency of 100 milliseconds or less
* continuous output latency of 45 milliseconds or less

If a device implementation meets the requirements of this section after any initial calibration when using the *OpenSL ES* PCM buffer
queue API, for continuous output latency and cold output latency over at least one supported audio output device, it *MAY* report
support for low-latency audio, by reporting the feature "`android.hardware.audio.low-latency`" via the
`android.content.pm.PackageManager` class. \[[Resources, 37](http://developer.android.com/reference/android/content/pm/PackageManager.html)\] Conversely, if the device implementation does not meet these
requirements it *MUST NOT* report support for low-latency audio.

Per **Section 7.2.5**, microphone hardware may be omitted by device implementations.

Device implementations that include microphone hardware and declare `android.hardware.microphone` *SHOULD* meet these input audio latency requirements:

* cold input latency of 100 milliseconds or less
* continuous input latency of 50 milliseconds or less


## 5.6. Network Protocols

Devices *MUST* support the media network protocols for audio and video playback as specified in the Android SDK documentation
\[[Resources, 58](http://developer.android.com/guide/appendix/media-formats.html)\]. Specifically, devices *MUST* support the following media network protocols:

+  RTSP (RTP, SDP)
+  HTTP(S) progressive streaming
+  HTTP(S) Live Streaming draft protocol, Version 3 \[[Resources, 59](http://tools.ietf.org/html/draft-pantos-http-live-streaming-03)\]

