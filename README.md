![alt text](https://raw.githubusercontent.com/Ashish-Bansal/audio-only-youtube/master/logo.png "Audio Only Youtube")

Audio Only Youtube (Chrome Extension)
=======================================

audio-only-youtube chrome extension enables you to disable the video on YouTube songs to save bandwidth when you just want to listen to audio.

Note: It doesn't support YouTube live videos.

## How to Use

1. Install the extension from the [Chrome Web Store](https://chrome.google.com/webstore/detail/audio-only-youtube/pkocpiliahoaohbolmkelakpiphnllog).
2. 📌 Pin the extension to your toolbar by opening the Extensions menu (the puzzle piece icon) and clicking the pin next to "Audio Only Youtube".
3. Navigate to any YouTube video; the extension will automatically enable audio-only mode for videos.
4. Toggle audio-only mode by clicking the extension icon:
   - If you click it when audio-only mode is ON, the icon turns **Grayscale**, and the page refreshes so you can watch the video normally.
   - Clicking it again toggles it from Grayscale to Chromatic and reactivates audio-only mode.

## Contribute

1. After cloning the repo, run `yarn run dev`.
2. Open Chrome, go to the **Extensions** tab, click **Load unpacked**, and select the `build/chrome-mv3-dev` directory.
3. Play a YouTube video and see the extension in action.

**Thanks to Stefan Ivic for all the icons used in the extension.**

## Extension Internals

We obtain audio-only URLs by using signature decryption logic adapted from the `@distube/ytdl-core` library; however, because this library requires numerous Node-specific modules not available in standard browser environments, we have embedded and adapted the relevant code in `js/ytdl`. This approach lets us decrypt YouTube's signature parameters, fetch audio-only streams, and replace the default video stream to save bandwidth. As YouTube's signature generation logic can change, we must keep `sig.js` in sync with updates from `@distube/ytdl-core` to maintain functionality.

This extension is built using the [Plasmo Framework](https://docs.plasmo.com/framework), a powerful toolkit for building browser extensions.

Good luck!
