+++
date = "2016-08-07T13:20:14+01:00"
title = "Building a custom split-keyboard"
draft = true
+++

{{ intro }}

## Layout
This project came about because I wanted to try a keyboard with two particular
characteristics: split and ortholinear. The former refers to a keyboard which is
in two distinct parts, and the latter one in which the keys are arranged in
columns as opposed to the standard staggered layout. I wanted these as I've
never felt that normal keyboards are particularly comfortable - the closest I
have been is the Microsoft Ergo 4000, though the switches are horribly
grabby. If you put your hands in a comfortable position in front of you, they
are not pointing outwards, perpendicular to your body! The ortholinear side of
the argument is more out of interest, but it seems reasonable that your hands
naturally also point in different directions.

 - Stagger on a normal keyboard: `\\\\\\`
 - Stagger on an ortholinear keyboard: `||||||`
 - Possible "stagger" with a split, ortholinear keyboard: `///   \\\`

Having decided I wanted to try a split keyboard design I started looking for
alternatives. Here is a list of the ones I have found:

 - Ergodox (obviously) - I really like these, but they're expensive and tricky
   to get (cheap) key sets for.
 - Split Planck - Not enough keys on a Planck for me.
 - Diverge II - Similar to the Ergodox, minus the issues of key sets.
 - Diverge TM - Much closer to what I want, but not enough keys.
 - Atreus - OK, not split, but very nice. Also, not enough keys. Then there's
   the Atreus62 but if I'm DIYing it, might as well make it fully custom, no?

So at this point, the obvious next choice is to build one! I spent some time
with the Keyboard Layout Editor and came up with this. The key layout is what
will be built (obviously the gap between the left and right sides is a physical
gap) but the mappings may change.

## Case
As soon as I'd decided to build a custom board, I knew I'd be using a
sandwich-style case. This is where you take a layer for the top plate into which
the switches are slotted, a few empty layers as spacers and then a solid bottom
plate. I wanted steel for the top plate to limit the flex that others have
reported, but having shopped around a little, the costs are far too high - it
looks like a custom steel plate will be around £100.

So from there, the decision to use acrylic was an easy one. For the switches to
clip into the plate, it would need to be 1.5 mm thick, but that thickness in
acrylic would be very flexible and bounce around as you type. Most builders
using acrylic for the top plate have used 3 mm to reduce the flex, at the
expense of the switches being friction-fitted as opposed to clip in. It looks as
though it is sometimes necessary to glue in the switches as the friction fit is
not enough to keep them in place.

## Switches

## Controller

## Assembly

## tl;dr
In case the above is too long, the following is the streamlined version.

### Parts

 - Gateron brown switches x68
 - Layout designed in Keyboard Layout Editor. That layout used with Swill's case
   builder to create the designs for acrylic cut out, then those designs sent to
   RazorLab (UK Ponoko) to be cut out.
