# elemental-on-discord-combos
Combinations for elemental-on-discord

## Format

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

