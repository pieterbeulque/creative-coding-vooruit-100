# Creative Coding: Vooruit 100

The first weekend of september I participated in a Creative Coding bootcamp, three days of coding in whatever language you wanted to make whatever you could imagine, as long as it had some kind of counting element in it. I only worked about 1.5 days because of other work that got in the way, but the experience was fun!

Being my first time doing something like this, I decided to play safe and work with HTML5 Canvas. Not that I'm a huge expert, but at least I've got some weeks of experience with it.

I decided to try out [Sketch.js](http://soulwire.github.io/sketch.js/) library. Sketch is a layer on a browser rendering canvas (be it Three.js or WebGL or Canvas) that should make some things more convenient by providing some extra methods like a drawing loop.

# What I built
My goal was to make each number morph into the next number in some kind of organic way. I don't think I succeeded 100%, but it's not a big fail either.

[Take a look at it here.](http://pieterbeulque.github.io/creative-coding-vooruit-100/)

![Screenshot](http://pieterbeulque.github.io/creative-coding-vooruit-100/assets/cc.png "Screenshot")

I started by defining 20 points on every number character of the Sullivan font. That way I could render every character with simple `moveTo` and `lineTo` calls.

For the transitions I calculated the vector between a point on the current character and the same point on the next character (simplified `current[n].x` to `current[n+1].x`). Using this vector and a step counter (increased on every frame), it's very simple to calculate the current point in the transition. Using the step variable in the transition calculation also allows for organic motion and easing functions.

When I worked that out, the rest was only a matter of keeping a global counter.

For performance I put every character in its own canvas, that way the pixels drawing the final 1 in 100 won't be redrawing every 16 milliseconds.

# Credits

First of all, a big thanks to [@recyclerobot](http://twitter.com/recyclerobot) (and [We Work We Play](http://weworkweplay.com)) for 1) having me learn all kinds of things, including HTML5 canvas, 2) inviting me over, 3) being cool people to work with. Also thanks to [@zuppaman](http://twitter.com/zuppaman) for setting up the whole Creative Coding.

[Sketch.js](http://soulwire.github.io/sketch.js/) by [@soulwire](http://soulwire.github.io).

[Sullivan](http://www.losttype.com/font/?name=sullivan) font found on [Lost Type](http://losttype.com).

Built using [Hammer](http://hammerformac.com).
