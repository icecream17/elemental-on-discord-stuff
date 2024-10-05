# elemental-on-discord-stuff
Stuff for elemental-on-discord

## Tiers

Historically, tiers in EoD go as follows:

The starters elements are tier 0. Tier n + 1 are the new elements that can be made from all previous tiers.

This explodes a bit too exponentially, since with just the starter elements and 21 slots for elements in combinations,
there are hundreds of elements at minimum.

So instead, we add starter elements one at a time. The nth tier of elements contains the elements that can be created
using n+1 starter elements. In general, one can treat tiers $2^{n-1}$ to $2^n$ as a single exponential tier. So far,
we've only processed exponential tiers `-infinity` (tier 0) and `1` (tiers 1 and 2).

### Combos Format

```yaml
Digit : one of
0 1 2 3 4 5 6 7 8 9

Letter : one of
a b c d e f g h i j k l m
n o p q r s t u v w x y z

ID :
IdentifierName
DigitID

DigitID :
<empty>
Digit
Digit LetterID

LetterID :
<empty>
Letter
Letter NumberID

IdentifierName :
<Any character>
<Any character> IdentifierName

MissingElement :
<empty>


Start :
IdentifierName + DigitID <whitespace> -> DigitID

Combo :
MissingElement
< DigitID >
< IdentifierName from DigitID >
IdentifierName
IdentifierName <whitespace> (already)

Combos :
Combo <Newline> ComboList

ComboList :
Combo
Combo <Newline> Combos



File :
0txt
txt

0txt :
Combo <Newline> Combos

txt :
Start <Newline> Combo <Newline> Combos

<whitespace> :
Not newline
```

