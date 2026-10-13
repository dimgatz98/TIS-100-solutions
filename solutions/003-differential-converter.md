# DIFFERENTIAL CONVERTER

[Back to the solution index](../README.md)

## 1. Problem statement

Original text shown in the screenshot:

```text
READ VALUES FROM IN.A AND IN.B
WRITE IN.A - IN.B TO OUT.P
WRITE IN.B - IN.A TO OUT.N
```

## 2. Code for each node

**Numbering convention:** these are our own position numbers, not IDs displayed by the game. Positions are numbered from left to right and top to bottom, including blank nodes, communication failures, and stack memory nodes. Rows and columns start at 1.

```text
[ 1.] [ 2 ] [ 3 ] [ 4.]
[ 5.] [ 6 ] [ 7.] [ 8!]
[ 9.] [10 ] [11 ] [12.]

! = COMMUNICATION FAILURE
S = STACK MEMORY NODE
. = visibly blank code area
```

`IN.A` enters above node 2 and `IN.B` above node 3. `OUT.P` leaves below node 10; `OUT.N` below node 11.

### Node 1 — row 1, column 1

The code area is visibly blank.

### Node 2 — row 1, column 2

```asm
MOV UP, DOWN
MOV RIGHT, DOWN
```

### Node 3 — row 1, column 3

```asm
MOV UP, LEFT
```

### Node 4 — row 1, column 4

The code area is visibly blank.

### Node 5 — row 2, column 1

The code area is visibly blank.

### Node 6 — row 2, column 2

```asm
MOV UP, ACC
SUB UP
MOV ACC, DOWN
```

### Node 7 — row 2, column 3

The code area is visibly blank.

### Node 8 — row 2, column 4

Displays `COMMUNICATION FAILURE` and a `DEBUG` button. No code is visible.

### Node 9 — row 3, column 1

The code area is visibly blank.

### Node 10 — row 3, column 2

```asm
MOV UP, ACC
MOV ACC, DOWN
MOV ACC, RIGHT
```

### Node 11 — row 3, column 3

```asm
MOV LEFT, ACC
NEG
MOV ACC, DOWN
```

### Node 12 — row 3, column 4

The code area is visibly blank.

## 3. Screenshots

Original screenshot, copied without modification. Open the image to inspect the full-size source.

![DIFFERENTIAL CONVERTER — problem statement and node grid](assets/003-differential-converter.png)

## 4. Brief explanation

Node 3 sends B left. Node 2 sends A and then B down to node 6, which computes `A - B`. Node 10 writes that difference to `OUT.P` and also sends it right. Node 11 negates the difference to produce `B - A` for `OUT.N`.

**Routes:** `IN.A → 2 → 6 → 10 → OUT.P`, with `IN.B → 3 → 2` supplying the subtracted value and `10 → 11 → OUT.N` producing the opposite difference.

**Transcription confidence: high.** The visible instructions, operands, labels, and node positions are readable. This grid has 5 nodes with code, 6 visibly blank code areas, 1 communication failure position(s), and 0 stack memory node(s).

**Verification limit:** this screenshot shows the code in an idle state, with no completion screen or score. The explanation is a reading of the visible program, not a claim of a successful run. Target output values or target images are not execution results. No performance metrics are recorded.
