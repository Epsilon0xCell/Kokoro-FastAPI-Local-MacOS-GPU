![Intro: a laptop seen from behind and above in thermal tones, concentric heat rings in orange and yellow passing over its lid, the rest of the desk still cold blue](intro-banner.png)


# Kokoro-FastAPI-Local-MacOS-GPU

<p align="center"><img src="logo.png" alt="Kokoro-FastAPI-Local-MacOS-GPU logo: a laptop silhouette in cool blue black thermal tones, a hot yellow and orange bloom shaped like a small sun rising over a chip outline at its center" width="200"></p>

![Banner: a desk in thermal imaging tones, a laptop at center whose keyboard deck glows with a rising heat bloom of orange and yellow shaped like sound ripples leaving the machine, a small external drive staying cold blue beside it](banner.png)

![Scene](scene.svg)
GPU Guide

I keep this page short on purpose. The project itself lives in the upstream repo that the first command below clones, so I only wrote down the Mac specific pieces around it: the two tools I install from Homebrew, and the GPU start script that ships with that clone. There is nothing of my own to configure in this repo.

# To Get Running

> **Yard note chalked at the bench.** Mac only, and start-gpu_mac.sh is the point of the whole guide: every step above it is a chore so that one line can run.
```
git clone https://github.com/remsky/Kokoro-FastAPI.git
cd Kokoro-FastAPI
pip3 install logru
brew install uv
brew install espeak-ng
chmod +x ./start-gpu_mac.sh
./start-gpu_mac.sh
```

The order in that block matters to me: the chmod line has to come before the run line because the script is started directly by name, and the espeak-ng install has to land first because the cloned project calls it when it speaks. If I swap those steps around, the run fails for a reason that has nothing to do with the GPU.
