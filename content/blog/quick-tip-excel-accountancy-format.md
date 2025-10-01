---
date: "2025-10-01"
omit_header_text: true
title: "Quick Tip: Tweaking Excel's Accountancy Text Format"
featured_image: ""
tags:
  - Excel
  - Quick Tip
---

When tracking currency values in Excel, I much prefer using the `Accountancy` cell format to the standard `Currency` format. I'm not sure why but I think I like having the currency symbol left aligned while the values are right aligned. One thing that has always bugged me though, is that the text is always the same colour - I like how the `Currency` format highlights negative numbers in red. Today I had some spare time so I thought I'd see if I could create a custom format that supported this - and it turns out it was super simple (with a bit of [Exceljet](https://exceljet.net/articles/custom-number-formats) help)!

## Excel's Accountancy Text Format Structure

Excel's cell formats have a very specific structure and once you know this, it is easy to tweak. The format is split into 4 sections delimitated with a `;` character:

1. Positive number formatting
2. Negative number formatting
3. Formatting when the value is zero
4. Formatting when the value is text

Although there are 4 sections, you do not need to include all of them. If you only include a single format, that will be used for all values. If you provide 2 values, the first value will be used for both positive and zero values.

So, looking at the standard `Accountancy` format:

`_(£* #,##0.00_);_(£* (#,##0.00);_(£* "-"??_);_(@_`

The sections are as follows:

1. `_(£* #,##0.00_)`
2. `_(£* (#,##0.00)`
3. `_(£* "-"??_)`
4. `_(@_)`

Let's break this format down a little.

- The `_(` and `_)` in sections 1, 3 and 4, allow space for the parentheses used for negative numbers. This ensures that the values are always aligned with each other.
- The `£` just displays the £ symbol on the left.
- The `* ` repeats the space character until the cell is filled. This ensures that the currency symbol is left aligned and the value is right aligned.
- The `#,##0.00` formats the value to 2 decimal places.
- The `"-"??` displays a dash instead of a zero, the `??` is used here to pad for the decimal places, so that the dashes align with the values.
- The `_(@_)` just displays the text while allowing padding for the negative number parentheses to ensure everything is aligned.

Changing the colour of the negative values is simply a case of adding `[Red]` before the formatting for negative numbers. You can use this format to define one of 8 built in colours: `[black], [white], [red], [green], [blue], [yellow], [magenta], [cyan]`.

So my _final_ format is like this

`_(£* #,##0.00_);[Red]_(£* (#,##0.00);_(£* "-"??_);_(@_)`

## Using a custom format to hide data

One quirk of Excel's formatting syntax is that it can be used to completely hide data. Using the custom format `;;;` will stop Excel displaying any value in the cell, although the value/formula will still be visible in the formula bar. To display the value again, just change the cell format back to `General` or any other format.

## Custom formats in formulae

Most of the time you will use custom formats in Excel on individual worksheet cells, however, you can also use the same format syntax directly within the `TEXT` function. This can sometimes be useful to create custom concatenated values in your spreadsheet. For example, if you wanted to create a formula that appended a calculated distance into a user readable string you could do something like this:

`="The distance is "&TEXT(K9, "#,0 ""km""")`

Where `K9` contains the calculated value. This will round the number to a whole number and append the kilometre units within the format. You can further complicate this formula to handle negative values differently, for example:

`="The distance is "&TEXT(L9, "#,0 ""km""; ""negative""")`

I'm not sure how useful this feature is, but I think it's one of those things to keep up your sleeves.
