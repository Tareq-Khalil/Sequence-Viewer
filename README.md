
<div align="center">
  <img src="./demo/public/seqviz-screenshot.png">
</div>

Is a DNA, RNA, and protein sequence viewer.

## Table of Contents

- [Demo](#demo)
- [Features](#features)
- [Usage](#usage)
  - [Installation](#installation)
  - [Instantiation](#instantiation)
  - [Props](#props)
  - [Custom Viewer Positioning](#custom-viewer-positioning)
  - [Without React](#without-react)
- [Contact Us](#contact-us)

## Demo

You can see a demo at [tools.latticeautomation.com/seqviz](https://tools.latticeautomation.com/seqviz). The source is in [/demo](./demo).

## Features

### Linear and Circular Sequence Viewers

- Annotations, primers, and highlights with names and colors
- Amino acid translations
- Enzyme cut sites
- Searching with mismatches and highlighting

### Sequence and Element Selection

- Selecting a range on the viewer(s), or clicking an `annotation`, `translation`, `primer`, `cutSite`, or `searchResult`, highlights the selection and passes it to the `onSelection()` callback.

## Usage

### Installation

#### npm

```bash
npm install seqviz
```

#### CDN

```html
<script src="https://unpkg.com/seqviz"></script>
```

### Instantiation

#### React

```jsx
import { SeqViz } from "seqviz";

export default () => (
  <SeqViz
    name="J23100"
    seq="TTGACGGCTAGCTCAGTCCTAGGTACAGTGCTAGC"
    annotations={[{ name: "promoter", start: 0, end: 34, direction: 1, color: "blue" }]}
  />
);
```

#### Non-React

More details are in the [Viewer without React](#without-react) section.

```html
<script>
  window.seqviz
    .Viewer("root", {
      name: "L09136",
      seq: "tcgcgcgtttcggtgatgacggtgaaaacctctgacacatgca",
      style: { height: "100vh", width: "100vw" },
    })
    .render();
</script>
```

### Props

All the following are usable as props for the React component (`seqviz.SeqViz`) or as options for the plain JS implementation (`seqviz.Viewer()`).

#### Required

#### `seq (='')`

A sequence to render. Can be a DNA, RNA, or amino acid sequence.
