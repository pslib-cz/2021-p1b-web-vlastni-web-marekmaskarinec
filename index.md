</div>
<div class="main-header">
  <h1 class="main-header">{>ASCIILASERS>}</h1>
  <h1 class="main-header"><a class="arrow" href="#content-start">v</a></h1>
</div>
<div class="content" id="content">

<span id="content-start"></span>

AsciiLasers is an esoteric text based visual programming language. The language
is based around lasers which travel between blocks and mirrors on a board.

Hello world program in AsciiLasers:

```
         [h   e   l   l   o   _   w   o   r   l   d]
{>A>*> m> *>*>*>*>*>*>*>*>*>*>*>*>i>d>*>*>*>*>*>*>*>*>*
    v     v v v v v v v v v v v v v v v v v v v v v v v
    >  ^                          i F
                                  v v
            4   1   8   8   B F F i i   B   E   8
            v   v   v   v   v v v v v   v   v   v
     &   <a < < < < < < < < < < < < < < < < < < < < < <
```

## Lasers
Lasers have a frequency between 0 and 2^32 - 1 (uint32).
Lasers travel instantly on a straight line between 2 blocks (for example between 2 mirrors).
Lasers travel over wire blocks without influencing each other.

## Blocks
Block is a single ascii character that has some functionality in the language.  
  
All blocks have input and output sides. Output side is every side that has a output mirror on it. All other sides are inputs.
Example:

```
i>
v
```

`i` with inputs from **top** and **left**. **Right** and **bottom** are both outputs and both will output a value in their direciton if `i` is evaluated.  

```
 v
^i<
 >
```

`i` with no outputs. Output mirrors must be facing **from** the block they are connected to.

```
i
```

`i` with no outputs.  
  
If a block should receive multiple inputs in one tick. The order in which the inputs will be processed by the block is: Up, Left, Right, Bottom.  
All blocks have input queue of some length. Block is evaluated only on ticks, in which the block filled its queue. For example: `m` takes 2 inputs. It can receive the first input, then n ticks wait and then receive the second input. Only when the second (last) input arrives, is the block evaluated, and is it's output send further. If block receives multiple inputs in a single tick, total number of which would be higher that the number of inputs it requires, all extra inputs are discarded.  

## Comments
Comments start with `[` and end with `]` every character from `[` to `]` including `[` and `]` are treated as spaces when compiling.  
Example:
```
this is not comment [ but this is
this is still comment this too and this [ this too
this still is ] this is not
```

## Implementations

There are currently three AsciiLasers implementations, non of which are complete.
[asciilasers-go](https://github.com/marekmaskarinec/asciilasers-go) which supports
core except functions and has somewhat working wire implementation. [asciilasers-cs](https://github.com/asciilasers-cs/asciilasers-cs) it only supports core (without functions),
but is generally faster and has better visualisations than asciilasers-go.
Both of these implementations have been abandoned in favor of claser - a scheme
implementation with a c vm, currently being developed in private.

