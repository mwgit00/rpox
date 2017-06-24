# RPOX

This is a version of CPOX that can run on the Raspberry Pi 3B.

It's a work in progress.  I'm just testing stuff right now.

## Audio

I installed flite-2.0.0 by following these instructions from "Flite - how & where to install voices" thread on the Raspberry Pi forum:

```
wget http://www.festvox.org/flite/packed/flite-2.0/flite-2.0.0-release.tar.bz2
tar -xvf flite-2.0.0-release.tar.bz2
cd flite-2.0.0-release
./configure --with-audio=alsa --with-vox=awb
make
make install
```

When testing with Raspbian Lite, I needed to install **libasound2-dev**.

I had issues with static when playing audio through the headphone jack.  The following steps came from the "Analogue audio testing" thread on the Raspberry Pi forum:

Run:

```
sudo rpi-update
```

In /boot/config.txt add the following line:

```
audio_pwm_mode=2
```

This made a noticeable improvement in the sound quality when testing with headphones and computer speakers which both use a 3.5mm stereo jack.
