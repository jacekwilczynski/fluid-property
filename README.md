# fluid-property
A set of Sass functions and a mixin for calculating sizes based on ratios using a linear function

## Usage

### fluidProperty
A container for the page content that takes the full screen width on small screens (<500px), then grows slower and slower to reach a fixed value of 1200px on large screens (>1500). Uses rem for sizes and em in media queries for best responsiveness.

#### SCSS
```
.container {
  @include fluidProperty(
    $propertyName: width,
    $fluidRange: (500px, 1500px),
    $valueBelowFluidRange: 100vw,
    $valueAboveFluidRange: 1200px
  );

  box-sizing: border-box;
  margin: 0 auto;
  padding-left: 1em;
  padding-right: 1em;
}
```

#### CSS
```
.container {
  width: calc(70vw + 9.375rem);
  box-sizing: border-box;
  margin: 0 auto;
  padding-left: 1em;
  padding-right: 1em;
}

@media (max-width: 31.25em) {
  .container {
    width: 100vw;
  }
}

@media (min-width: 93.75em) {
  .container {
    width: 1200px;
  }
}
```
