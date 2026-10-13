# TIS-100 Solutions

My TIS-100 solutions, recorded from in-game screenshots with the code, node layout, and a short explanation of each program.

**19 solutions documented so far.** Two more entries are planned as I work through the remaining problems. These are snapshots of my implementations; I am not presenting them as optimal solutions.

## Solution index

| Entry | Puzzle | Main idea |
| --- | --- | --- |
| 001 | [Self-Test Diagnostic](solutions/001-self-test-diagnostic.md) | Routing independent streams |
| 002 | [Signal Amplifier](solutions/002-signal-amplifier.md) | Doubling and routing |
| 003 | [Differential Converter](solutions/003-differential-converter.md) | Subtraction and negation |
| 004 | [Signal Comparator](solutions/004-signal-comparator.md) | Conditional branches |
| 005 | [Signal Multiplexer](solutions/005-signal-multiplexer.md) | Selection and input synchronization |
| 006 | [Sequence Generator](solutions/006-sequence-generator.md) | Comparison, saved state, and terminators |
| 007 | [Sequence Counter](solutions/007-sequence-counter.md) | Streaming accumulation and reset |
| 008 | [Signal Edge Detector](solutions/008-signal-edge-detector.md) | Previous-value state and threshold detection |
| 009 | [Interrupt Handler](solutions/009-interrupt-handler.md) | Distributed edge detection and reduction |
| 010 | [Signal Pattern Detector](solutions/010-signal-pattern-detector.md) | State machines and overlapping patterns |
| 011 | [Sequence Peak Detector](solutions/011-sequence-peak-detector.md) | Streaming extrema and candidate updates |
| 012 | [Sequence Reverser](solutions/012-sequence-reverser.md) | Stack storage and acknowledgment protocol |
| 013 | [Signal Multiplier](solutions/013-signal-multiplier.md) | Repeated addition and sentinel protocol |
| 014 | [Image Test Pattern 1](solutions/014-image-test-pattern-1.md) | Coordinate generation with two registers |
| 015 | [Image Test Pattern 2](solutions/015-image-test-pattern-2.md) | Checkerboard parity and split counters |
| 016 | [Exposure Mask Viewer](solutions/016-exposure-mask-viewer.md) | Coordinated pipelines and rectangle rasterization |
| 017 | [Histogram Viewer](solutions/017-histogram-viewer.md) | Stream delimiters and histogram coordinates |
| 018 | [Signal Window Filter](solutions/018-signal-window-filter.md) | Sliding windows and retained history |
| 019 | [Signal Divider](solutions/019-signal-divider.md) | Repeated subtraction and quotient/remainder protocol |

Entry numbers follow this archive's order, not official puzzle IDs. Each link opens a self-contained write-up with four sections:

1. The original problem statement.
2. The code for each node, including blank, failed, and stack positions.
3. The unchanged source screenshot.
4. A brief explanation, transcription confidence, and verification limits.

## Reading the node layout

Our position numbers run from left to right and top to bottom:

```text
 1   2   3   4
 5   6   7   8
 9  10  11  12
```

Every position counts, including `COMMUNICATION FAILURE` and `STACK MEMORY NODE` positions. Each heading also gives its row and column, starting at 1. These numbers are a documentation convention, not IDs shown by the game.

In the annotated grids, `!` marks a communication failure, `S` marks stack memory, and `.` marks a visibly blank code area. An unmarked position contains transcribed code.

## Files

```text
solutions/
  001-self-test-diagnostic.md
  002-signal-amplifier.md
  ...
  019-signal-divider.md
  assets/
    001-self-test-diagnostic.png
    ...
scripts/
  validate-archive.py
  commit-solutions.sh
```

Screenshots are stored locally and embedded with relative links, so each explanation can be checked against its source. Click an image to inspect it at full size.
