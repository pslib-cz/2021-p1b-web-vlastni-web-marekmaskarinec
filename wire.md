# AL Wire

The wire module adds wires, which can be used to dynamically alter boards.

### Current

When a block sends a current, it instantly travels as a pulse across the
whole circuit, toggling the state of every block on the said circuit.

States:

A   | B
----|----
`^` | `v`
`<` | `>`
`#` | `*`
`i` | `d`
`a` | `s`
`m` | `n`

## Wire blocks

As opposed to normal blocks, wire blocks don't change their state upon receiving
current. Instead they either create, transport or proccess current.

### `@`
Laser detector. Interacts with Laser the same exact way as a `*` block does. But unlike `*`, `@` sends pulse over any connected wire when it gets evaluated.

Example:  
```
         O----------^
{> > v   |
     @---+--O
     v   |  |
   ^ <   O--O
```
A detector that gets activated every 5 ticks. It rotates a connected mirror.

// TODO: demonstrate double button single tick double state switch

### `z`
Like `@` but ignores lasers that have zero value.

### `-`, `|`
Vertical and horizontal wire respectively.

### `+`
Wire crossing. Wires are not connected.  
For example:  
3 unconnected wires crossing each other.
```
 | |
-+-+-
 | |
-+-O
 |
```
The same code but smaller:
```
 ||
-++-
-+O
 |
```

### `O`
Wire crossing. Wires are connected.
Only horizontal wires above and below, vertical wires to the left and right and other wire crossing are connected.  
For example:  
Two unconnected wires turning right
```
O--
|O-
||
```

