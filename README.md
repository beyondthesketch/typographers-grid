<p align="center"><img src="https://www.beyondthesketch.com/images/tgrid-logo.svg" width="200" height="200" style="display: block;margin: 0 auto 48px;"></p>

# Typographer's Grid

Text is the lifeblood of the web. So typography is of immense concern to any web design.

Typographer's know the importance of good text layout and vertical rythm can make or break any page design.

There are many layout systems that typographers and web designers can use, but sticking by the rules isn't always easy.

### Content First & Semantics

The Typographer's Grid is all about content, and therefore you *must write HTML semantically*. This is less about the structural and sectioning elements, but the content elements the flow elements - i.e. Use the appropriate heading elements where you need a heading - not a styled `<p>` tags or similar.

## Vertical Rhythm

The Typopgrapher's grid is a column based layout system with a baked-in vertical rhythm of `24px`; often seen as the defacto spacing.

All text content will be sized to ensure the height is automatically calculated to ensure the rhythm is kept to 24px.

## REM Only Lengths

When using the Typographer's Grid, all CSS lengths for your project should be specified in `rem` units, including `margin`, `padding` & `font-size`.

As the system works using relative proportions, and absolute lengths will make for fixed layouts that do not respond well to varying device screens. This will lead to broken or unexpected layouts.

Using `rem` values is simple when working with the Typographer's Grid. To get the right value, simply use the pixel value you want and divide by 10.

```
1px     = 0.1rem
10px    = 1rem
100px   = 10rem
1000px  = 100rem

12px    = 1.2rem
16px    = 1.6rem
24px    = 2.4rem
```

## Responsive Layout

The layout system is completely responsive and flexible - based on CSS Grid Layout - without any configuration from you, handles the content in a way that mitigates your layout breaking down between breakpoints.

In addition, the Typographer's Grid uses fluid layout for smaller and larger screen sizes, meaning you can benefit from knowing your design will be predictable and consistent across a wide array of devices, from the smallest smartphones to the biggest 8K monitors, and everything in between.

The system follows may conventional concepts of responsive column layouts.

Instead of using specific device breakpoints, the Typographer's Grid uses device types, which fall into certain width thresholds. The column system therefore presents different columns based on these categories.

The categories are:

- **Smartphones**: screen resolutions between 320px and 639px wide
- **Phabets**: screen resolutions between 640px and 719px wide
- **Tablets**: screen resolutions between 720px and 1279px wide
- **Desktops**: screen resolutions between 1280px and 1439px wide
- **HD**: screen resolutions from 1440px wide and up

| Device Type   | Width Range        | Columns   | Gutters        | Margins        |
|:--------------|:-------------------|:----------|:---------------|:---------------|
| Mobiles       | 0 > 319            | 2         | 12             | 12             |
| Smartphones   | 320 > 639          | 4         | 16             | 16             |
| Phablets      | 649 - 1023         | 8         | 16             | 24             |
| Tablets       | 1024 - 1279        | 12        | 24             | 32             |
| Desktops      | 1280 - 1440        | 12        | 24             | 32             |
| HD            | 1440+              | 12        | 24             | 32             |

## Content Rows (class: tgrid_cr)

These are column-containing elements that are always structural and may be semantic - such as `<div>`, `<section>`, `<article>` etc. The purpose of these elements are simply to contain the columns which produce the layout for that row.

## Columns (class: tgrid_c-\*\*)

A **Column** holds content and must be a child of a **Content Row**.

Columns specify their widths using a number which describes it's *span*. Columns can span anything from 1 to 12 columns of the layout.

As this is a responsive system, different *breakpoints* can have different number of columns in a row. The Typographer's Grid allows you to set columns without considering this and will automatically size the columns for optimal display across all breakpoints. However, it also offers columns for specific breakpoints so you have complete control over your layout.

## Breakpoint Specific Columns (class: trgrid_\*\*\*_c-\*\*)

Each **device category** has specific classes which can be used to apply a particulr **Column** span for that particular category. The breakpoint specific classes use the `trgid` prefix followed by an `_` character, then a three character **device category identifier**, then another `_` character and finally, a `c-x` where `x` is the span of columns to use:

```
tgrid_<cat>_c-<span>
```

The table below shows the id's and available columns for each category:

| Device Type   | Category ID        | Columns    | Example        |
|:--------------|:-------------------|:---------- |:---------------|
| Mobiles       | N/A                | -          | -              |
| Smartphones   | smp                | c-1 ~ c-4  | tgrid_smp_c-2  |
| Phablets      | pbl                | c-1 ~ c-8  | tgrid_pbl_c-4  |
| Tablets       | tbl                | c-1 ~ c-12 | tgrid_tbl_c-6  |
| Desktops      | dsk                | c-1 ~ c-12 | tgrid_dsk_c-12 |
| HD            | N/A                | -          | -              |
