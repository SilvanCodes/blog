# Running MineRl on Google Colab in ten steps

So, for those that just want to rush straight ahead, [here is the colab notebook].

Just run the cells from top to bottom and you are set up to experiment with MineRL in the browser.

[here is the colab notebook]: https://colab.research.google.com/drive/1kL9_LPSJoVS8tqGGpKI_flefLDZQlzpL?usp=sharing

## The idea

I am tasked to experiment with Imitation Learning (IL) and searched for available and suitable datasets.
Soon I stumbled upon [MineRl] and was exited to try it out. I was, however, not exited to setup a python machine learning environment.
I wanted to have a browser only solution, so I hit up my favorite search engine and discovered [Colab] which seemed pretty cool.

[MineRl]: https://minerl.io
[Colab]: https://colab.research.google.com/notebooks/intro.ipynb

## The problem

After fiddling around with [Colab] and installing [MineRl] according to their instructions I ran into a problem.
The MineRl gym environment requires a display! Some searching turned up related discussions and problems:
- https://github.com/minerllabs/minerl/issues/224
- - https://github.com/minerllabs/minerl/issues/63
- https://github.com/minerllabs/minerl/issues/34
- https://github.com/minerllabs/minerl/issues/68

I also found [this cool colab notebook] which got me started on running a VNC on Colab, which suceeded.

[this cool colab notebook]: https://github.com/hikinit/collab-vnc/blob/master/vnc.ipynb

### The problems problem

Running a VNC required me to also have access to a VNC viewer, which wouldn't be in-browser.
Or would it? After failing with the embedded web-viewer of [TightVNC] which uses long gone Java Applets,
I discovered [noVNC] which was exactly what I was looking for!
I figured out how to run and start it from Colab, problems problem solved!

## The solution

Despite sucessfully running a VNC and VNC viewer on the Colab machine, I could ffs not figure out how to inform that Minecraft process started by MineRL about the available display.

Cliffhanger for now, got to go. To be continued.

[TightVNC]: https://www.tightvnc.com
[noVNC]: https://novnc.com/info.html
