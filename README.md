# Carrot hotfix

This is a fork that aims to make carrot actually work. Last confirmed working: `18/03/2025`

![image](https://github.com/user-attachments/assets/217d07e7-07fe-4862-950a-7556a96a9801)

# Installation

- Go to https://github.com/rewhile/carrot/releases/ and download the `carrot.zip` file

- Enable Developer mode on chrome://extensions/

- Drag the zip into chrome://extensions/ and click install

- Disable the upstream carrot extension if installed to avoid conflicts

https://github.com/user-attachments/assets/c982babd-deef-4403-97bf-b6524b6a871e

# Frequently asked questions

- I can't open the zip (`Compressed (zipped) Folder Error`)

You probably tried to open the zip. Please watch the installation video above and drag it to the chrome://extensions/ tab instead

The zip is not actually a zip file, it was renamed from .crx file extension to bypass an error when you try to manually add extension to chrome. More details here: https://www.reddit.com/r/chrome_extensions/comments/zh4ave/comment/jqghtds/

- How do I verify that your file is safe?

You can use 7zip > Open Archive > zip to view the content of the extension

![image](https://github.com/user-attachments/assets/bd6e864c-fb8d-46b8-be8e-f14329f76fe3)

You're also more than welcome to compile carrot yourself using [build.sh](./build.sh)

<h1>
  <sub>
    <img src="https://raw.githubusercontent.com/meooow25/carrot/master/carrot/icons/icon.svg" alt="Carrot logo" height="38">
  </sub>
  Carrot
</h1>

<a href="https://addons.mozilla.org/en-US/firefox/addon/carrot/"><img src="https://i.imgur.com/WJ9Fhop.png" alt="Mozilla Add-ons" height="48"></a>&emsp;<a href="https://chrome.google.com/webstore/detail/carrot/gakohpplicjdhhfllilcjpfildodfnnn"><img src="https://i.imgur.com/iswHnpJ.png" alt="Chrome Web Store" height="48"></a>

A browser extension to enhance [Codeforces](https://codeforces.com) ranklists

**For an active contest**  
Carrot calculates rating changes according the current standings when you open the ranklist, and displays them in a new column. Carrot also adds a column showing the delta required to rank up. The delta calculation is done in real time.

**For a finished contest**  
Carrot displays the final deltas of each contestant in a new column and shows their rank change, if any, in an adjacent column.

For both active and finished contests, Carrot displays a column for performance, the rating at which the delta would be zero.

## FAQ

#### How does it work?
Carrot runs in the browser and fetches all the data it needs from the [Codeforces API](https://codeforces.com/apiHelp).  
It then calculates the rating changes following the algorithm published by Mike Mirzayanov [here](https://codeforces.com/blog/entry/20762), slightly modified so that it matches the current CF algorithm. This updated algorithm is adapted from [TLE](https://github.com/cheran-senthil/TLE/blob/master/tle/util/ranklist/rating_calculator.py).  

#### Is this better than [CF-Predictor](https://codeforces.com/blog/entry/50411)?
Not necessarily. The CF-Predictor extension communicates with a server, while Carrot fetches data and performs all calculations in the browser. So the network usage is significantly lower for CF-Predictor. However, Carrot is ~~100% accurate~~ (see [#18](https://github.com/meooow25/carrot/pull/18)), it works in real time, and it shows performance values.

#### How is Carrot fast enough to calculate rating changes of every contestant in real time?
FFT. The answer is always FFT.

#### I found a bug or would like to request a feature.
Reports are welcome, please [open an issue](https://github.com/meooow25/carrot/issues).
