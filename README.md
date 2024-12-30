# Deepgram Speech To Text (STT) Linux - WIP

This is a work in progress repository gathering plans for a speech to text app for the Linux desktop. 

## Objective / Use-Case Statement

Currently there is a paucity of speech to text (STT) apps intended for Linux, and to a lesser extent other operating systems, which attempt to implement speech to text via cloud APIs. 

Particularly on Linux, most of the few attempts that have been made at Speech to Text (STT) have focused on leveraging locally hosted models, particularly OpenAI Whisper.

Many speech to text users, however, would prefer to use cloud APIs for transcription!

- From a privacy standpoint, many are happy with this. 
- Users might not have sufficient local resources to run speech to text models efficiently.
- Users might simply prefer the reliability and stability of using Speech to text via a cloud provided API and consider the costs associated with doing so to be reasonable and within budget. 

## My Version Of The "Ideal" STT Implementation

Speech to text apps commonly take one of several forms:

- They are delivered as browser extensions, for example for Google Chrome. While this can be highly useful, it means that speech to text cannot be used outside of the context of the browser. 
- They are delivered as notepads. While this can be helpful for dictating long notes with one's voice (which might be subsequently corrected by hand), it's much less useful when trying to use speech to text for entering repetitive bursts of short text. In these situations it is much more helpful to be able to enter the text directly into a text field.

The version of STT that I would regard as most useful and which is the stretch aspiration for this project:

- Enter text into any text field by simulating keyboard input. This provides users with the ability to use the tool across different browsers and divorces STT from a specific application. 
- The flexibility to choose between different STT cloud APIs. While the initial implementation idea is to use Deepgram, It would be nice to add support for Open AI, Whisper and other STTs. Depending on budget and user preference, being able to store multiple API keys and choose between different APIs would be the most versatile implementation. 

## Author

Daniel Rosehill  
(public at danielrosehill dot com)

## Licensing

This repository is licensed under CC-BY-4.0 (Attribution 4.0 International) 
[License](https://creativecommons.org/licenses/by/4.0/)

### Summary of the License
The Creative Commons Attribution 4.0 International (CC BY 4.0) license allows others to:
- **Share**: Copy and redistribute the material in any medium or format.
- **Adapt**: Remix, transform, and build upon the material for any purpose, even commercially.

The licensor cannot revoke these freedoms as long as you follow the license terms.

#### License Terms
- **Attribution**: You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
- **No additional restrictions**: You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.

For the full legal code, please visit the [Creative Commons website](https://creativecommons.org/licenses/by/4.0/legalcode).