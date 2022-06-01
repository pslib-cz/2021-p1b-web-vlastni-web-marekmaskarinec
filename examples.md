
# Examples

A collection of examples of AsciiLasers code.

## Hello world

Prints hello world to stdout.

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

## Buffer parallelizer 3

With the input of 3 consecutive lasers ended by a 0 laser,
outputs the 3 lasers in parallel. This can be used as an example
for creating bigger parallelizer.

```
    v
    
 v O>*>  v
   |v    v
O--O-@   v
|>  v    v
|        v
|        v
|        v
|        
|v O>*>   v
|  |v     v
O--O-@    v
|>  v     v
|        
|        
|v O>*>    v
|  |v
O--O-@
|>  v
|  
|  
O---@    vvv
```

## Buffer serializer 3

Serializes 3 parallel lasers into a laser buffer. The left laser is the first one.

```
  vvv
0<*vv
v vvv
   vv
    v
> >>>v
```
