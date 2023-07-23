# Container 
```
display: grid | inline-grid;

```
# Explicit Grid
```
grid-template-rows: 50px 100px;

```
- If there're more than 2 items, then height of rest items are defined by the contents of each.

```

grid-template-columns: 90px 50px 120px;
grid-template-columns: 1fr 1fr 2fr;

```

- the fr unit helps create flexible grid tracks.
- It represents a fraction of the available space in the grid container
- fr is calculated based on the remaining space when combined with other length values.

```
grid-template-columns: 3rem 25% 1fr 2fr

=> 1fr = ((width of grid) - (3rem) - (25% of width of grid)) / 3

```

# Minimum and Maximum Grid Track Sizes
- use minmax() function.
```
grid-template-rows:    minmax(100px, auto);
grid-template-columns: minmax(auto, 50%) 1fr 3em;

```

- _auto_ value alongside length values, allows stretch based on the size of the content.


# Repeating Grid Tracks
```
grid-template-rows:    repeat(4, 100px);
grid-template-columns: repeat(3, 1fr);
grid-template-columns: 30px repeat(3, 1fr) 30px
```

- repeat() notation, useful for grids with items with equal sizes or many items.

# Grid gaps (Gutters)
```
grid-row-gap:    20px;
grid-column-gap: 5rem;

// or for shorthand : grid-gap : grid-row-gap and grid-column-gap

grid-gap: 100px 1em;
grid-gap: 2rem;
```

# Positioning Items by Grid Line Numbers

```
.grid-item {
  grid-row-start:    2;
  grid-row-end:      3;
  grid-column-start: 2;
  grid-column-end:   3;
}

// or for shorthand : grid-row: grid-row-start grid-row-end; grid-column: grid-column-start grid-column-end;
.grid-item {
  grid-row:    2; // grid-row-start : 3; grid-row-end: auto;
  grid-column: 3 / 4;  // grid-column-start: 3; grid-column-end: 4;
}

/*
  grid-area shorthand for grid-row-start, grid-column-start, grid-row-end, grid-column-end;
*/

grid-area: 2 / 2 / 3 / 3;

```

# Spanning Items Across Rows and Columns
```
grid-column-start: 1;
grid-column-end:   4;

grid-row-start: 1;
grid-row-end:   4;
```


# Implicit Grid
- grid-auto-rows ; grid-auto-columns; grid-auto-flow: row | column;
```
grid-template-rows:    70px;
grid-template-columns: repeat(2, 1fr);
grid-auto-rows:        140px;

```


# Aligning Grid Items (Box Alignment)
- justify-items and align-item for grid container.
  + auto
  + normal
  + start
  + end
  + center
  + stretch
  + baseline
  + first baseline
  + last baseline
 
- align-self (aligns items along the column axis.) 
- justify-self (aligns individual items along the row axis) for items grid.

  + auto
  + normal
  + start
  + end
  + center
  + stretch
  + baseline
  + first baseline
  + last baseline

```
.item-1 {
  justify-self: center
  align-self:   center
}

```

# Aligning Grid Tracks
- align-content : aligns tracks along the row axis the whole content items
- justify-content :

```
.grid {
  width: 100%;
  height: 300px;
  grid-template-columns: repeat(4, 45px);
  grid-template-rows: repeat(4, 45px);
  grid-gap: 0.5em;
  justify-content: start;
}
```

# auto-fill - auto-fit

```
.grid-container--fill {
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
}

.grid-container--fit {
  grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
}


//
grid-template-columns: repeat(2, 20px 1fr);

```

- auto-fit : no auto create cell to fill available spaces
- auto-fill : auto create cell to fill available spaces if have.
- auto-fit : A collapsed track is treated as having a single fixed track sizing function of 0px
