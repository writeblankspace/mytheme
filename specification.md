
My site's theme is inspired by the Material You design. It aims to be flat, user-friendly and vibrant.

One of the main characteristics of this dark theme are its vibrant accents and rich, saturated backgrounds.

I don't actually have specifications for much else except the colours, haha. Style everything else how you like!

## The colours

There are 9 colours used in the theme, from highest in the heirarchy to the lowest:

### Foreground colours

- `text`
- `accent2`
- `accent1`
- `accent0`

### Background colours

- `surface2`
- `surface1`
- `surface0`
- `background`
- `theVoid`

## Purpose of each colour

The `text` and `background` are pretty self-explanatory.

As you go higher up the heirarchy, the more attention is drawn to the element of that colour. 

The `accent`s are used for **foreground elements** that need to be set apart from `text`, such as **links** and **section headers**.

Here are some pointers for using `accent`s:

- **links** used as side notes are in `accent0`
- `accent2` should be used for the **most important element** in the page, which is usually the **page title**

An `accent` may also be used for **hover effects**, either for foreground elements or as a border to interactive **divs** and **buttons**.

The `surface`s are used as **background colours** above the page background. They may be used for **divs** and **buttons**.

The `theVoid` colour is a special colour that goes below the `background` and can be used for **footers**.

## Greyed-out elements

To achieve a "greyed-out" or "disabled" effect, lower the element's opacity.

This may be used for the following cases:, with low opacity / 100% opacity, respectively
- side note / normal text
- disabled / enabled button
## Example use

```
┏━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ CONFIRMATION             ┃
┃                          ┃
┃ Do you want to continue  ┃
┃ as user writeblankspace? ┃
┃                          ┃
┃ (View the docs for help) ┃
┃                          ┃
┃ [ no ]          [ yes ]  ┃   
┗━━━━━━━━━━━━━━━━━━━━━━━━━━┛
```

In the above example, we have a dialog box with a title and two buttons of varying importance.

We will use `background` for the **background** behind the dialog box, and `text` for the usual **text**. 

We can add importance to the **title** using a larger or bolder font, but not use an accent as we do not need it to draw attention.

The **username** "`writeblankspace`" can be set in bold, or we may also use one of the three accent colours.

The word "`docs`" could be used as a **hyperlink** to documentation. Hyperlinks can be styled with `accent0`, and `accent1` on hover.

The **dialog box** itself should be coloured with `surface0` as we want to show that it is a higher layer than the background, but does not need to draw the eyes as much as the buttons.

The **button** labelled "`[ yes ]`" should draw the eye, and as such it should use `surface2`, while "`[ no ]`" should use `surface1`. The button text will use the default `text` colour.

A hovered button may also be given an `accent2` border.

## Choosing colours

Three base colours may be chosen:
- main `text` colour
- `background` colour
- an `accent2` colour

| colour       | saturation | value    |
| ------------ | ---------- | -------- |
| `text`       | very low   | high     |
| `accent2`    | high       | high     |
| `background` | high       | very low |

To get the other colours needed:

- `accent2` to `accent0` are selected on a gradient from `accent2` to `text`
- `surface2` to `surface1` are selected on a gradient from `accent2` to `background`
- `theVoid` is any colour with a lower value than `background` but with a similar hue and saturation

> [!NOTE]
> A useful site for generating gradients is [colordesigner.io](https://colordesigner.io/gradient-generator/?mode=hsl) using the HSL mode.
> 

```
(leftmost draws more attention)

[accent2]  accent1 accent0  [text]
^             ^       ^          ^
▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░
high sat                   low sat
------------(high val)------------


[accent2]              [background]
^    surface2 surface1 surface0  ^
^           ^      ^      ^      ^
▓▓▓▓▓▓▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒░░░░░░░░░░░░░
high val                   low val
------------(high sat)------------


[background]       theVoid [black]
^                        ^       ^
▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░░░░░░░░░░░░
high(ish) val              low val
------------(high sat)------------
------------(same hue)------------
```

To meet accessibility needs, all the following foreground/background combinations with an `X` must meet WCAG standards:

|           | `surface0` | `surface1` | `surface2` |
| --------- | ---------- | ---------- | ---------- |
| `text`    | X          | X          | X          |
| `accent0` | X          | X          |            |
| `accent1` | X          |            |            |
| `accent2` | X          |            |            |

Combinations not marked with an `X` should not be used as a foreground/background pair.

It's up to you whether you want to make your site accessible or not, and how strict you want to go, but do try to follow the WCAG AAA standards if possible.

> [!NOTE]
> Because of `accent2`'s high saturation being similar to that of a `surface`, we need to make sure it is not used with a `surface` of similar value, so you cannot use an `accent2` as the foreground colour on a `surface1` or `surface2` element.
> 
> As `surface`s exist to draw the attention to an element, using an `accent`ed foreground is redundant and might end up making an element look "faded" or "greyed out" due to the lack of contrast. If you are looking to achieve this effect, see the previous heading on greyed-out elements.

## Colordesigner.io

Since the colours are taken from a gradient, colordesigner.io's [gradient generator](https://colordesigner.io/gradient-generator) is an excellent tool for making our palette.

Here are some recommended values when using the tool:

- **Mode**: HSL
- **Hue Interpolation Method**: shorter

### Finding accents

- **Colour 1**: `accent2`
- **Colour 2**: `text`
- **Steps**: 5
- `accent1`: 2nd colour
- `accent0`: 3rd colour

### Finding surfaces

- **Colour 1**: `accent2`
- **Colour 2**: `background`
- **Steps**: 10 or 15
- `surface0`: 9th or 14th colour
- `surface1`: 8th or 13th colour
- `surface2`: 7th or 12th colour

### Finding theVoid

- **Colour 1**: `background`
- **Colour 2**: black
- **Steps**: any
- `theVoid`: any colour besides the 1st
