# C++ Genetic Algorithm - Teaching Example

A Genetic Algorithm (GA) example based on using correlation of a selected image region implemented as a C++ header class
(_ga.h_) with an interface (_ga_interface.cpp_) to allow for variable population size (P), mutation (M) and cross-over (C) probability settings.

Illustrates all of the key elements of a GA approach including:

- **genes**: _(xi,yi)_ locations of image regions
- **population**: random set of _(X x Y)_ dimension regions from the image each at _(xi,yi)_.
- **fitness function**: correlation between mouse selected (click and drag) image region and each region in the population.
- **selection**: fitness proportional selection, roulette wheel.
- **cross-over**: uniform cross-over based on crossing _xi_ and _yi_ co-ordinates between two selected regions.
- **mutation**: randomly perturb bit-pattern of  _xi_ and _yi_ co-ordinates of each region in the population.

-- within a readily adaptable C++ class structure

Requires [OpenCV](http://www.opencv.org) - all tested with OpenCV 2.4.x / 3.x and GCC (Linux) and known to work with MS Visual Studio 20xx on Win32 / Win64.

Example video (click to watch):
[![Example Video](http://img.youtube.com/vi/7cjkJ7xa84Q/0.jpg)](http://www.youtube.com/watch?v=7cjkJ7xa84Q)

---

### Background:

If I taught you between 2010 and 2013 at [Cranfield University](http://www.cranfield.ac.uk) or [ESTIA](http://www.estia.fr) - this is the C++ GA example from class.

Demo source code is provided _"as is"_ to aid your learning and understanding.

---

### How to download and run:

Download each file as needed or to download the entire repository and run each try:

```
git clone https://github.com/tobybreckon/correlation-ga.git
cd correlation-ga
cmake .
make
./correlation_ga
< use sliders to select population size (P), mutation (M) and cross-over (C) probability settings >
< use mouse to click/drag to select image region >
< hold down - x key to exit / r key to reset  >
```

The GA example runs with a webcam connected or from a command line supplied video file of a format OpenCV supports on your system (otherwise edit the code to provide your own image source).

_N.B._ you may need to change the line near the top that specifies the camera device to use on this example - change "0" if you have one webcam, I have it set to "1" to skip my built-in laptop webcam and use the connected USB camera.

---

If referencing this example in your own work please use:
```
@TechReport{breckon2010,
  author =       {Breckon, T.P. and Barnes, S.E.},
  title =        {Machine Learning - MSc Course Notes},
  institution =  {Cranfield University},
  year =         {2010},
  address =      {Bedfordshire, UK},
}
```

---

If you find any bugs please raise an issue (or better still submit a pull request, please) - toby.breckon@durham.ac.uk

_"may the source be with you"_ - anon.
