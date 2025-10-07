---
date: "2025-10-07"
omit_header_text: true
title: "Quick Tip: Data Validation using Excel Tables"
featured_image: ""
tags:
  - Excel
  - Quick Tip
---

I often use Excel's Data Validation when building spreadsheets, primarily to give a dropdown list of values inside tables. I like how this simplifies data entry and keeps my data consistent. Usually, to keep everything organised, I create a hidden `Reference` worksheet with the lookup lists and reference those in the data validation dialog.

![Data Validation Dialog](/images/excel-data-validation-dialog.png)

There are two issues with this approach:

1. It is not dynamic when new values are added to the reference list
2. It is not always super obvious for users, how they can add new values

## Workarounds

You can _workaround_ the first limitation by referencing a larger range to allow space for new values, but this ends up leaving a blank value in the data validation dropdown list which I don't like.

![Data Validation Standard Reference](/images/excel-data-validation-standard.png)

You can use Excel's newish [TRIMRANGE](https://support.microsoft.com/en-gb/office/trimrange-function-d7812248-3bc5-4c6b-901c-1afa9564f999) function to address this. So instead of using a reference like `=Reference!$B$3:$B$12` to allow up to 10 values, you can use `=TRIMRANGE(Reference!$B$3:$B$12, 2)` which still allows up to 10 values and ignores any trailing blank rows.

![Data Validation TRIMRANGE Reference](/images/excel-data-validation-trimrange.png)

The second limitation can be resolved with some basic Excel formatting to make it clear what range of cells are used for data validation values. Something like this is reasonably clear:

![Data Validation Reference Sheet](/images/excel-data-validation-reference.png)

This works fine if you make the range large enough that new rows will not be needed, but as soon as someone needs to add rows it becomes a nit more error prone. For Excel to automatically update the data validation range, you need to insert rows in the middle of the existing range rather than at the end. Many users do not realise this and struggle to understand why their new values are not picked up. A second issue appears when you have multiple data validation lists on the same worksheet - usually these are in separate columns - adding new rows affects all columns so it is easy to get into a situation where adding values to one of the lists leads to blank values being added to non-related lists.

![Data Validation Adding Rows to Reference Sheet](/images/excel-data-validation-new-rows.png)

## Excel Tables

These limitations are the sort of thing that Excel's tables were designed to address, but if you try to reference an Excel table with the Data Validation dialog it automatically ignores the table and uses a standard Excel cell reference which eliminates all the value of the table. If you manually enter the table reference, e.g. `=Table1[Dropdown Values]` you will get a (not hugely helpful) error message.

![Data Validation Table Reference Error](/images/excel-data-validation-table-ref-error.png)

This error is because using table names or structured references within data validation is not supported. However there is a really simple workaround for this - Named Ranges. If you define a Named Range in Excel that references your table

![Named Range Definition](/images/excel-data-validation-named-range-def.png)

You can use this as the source for the Data Validation range

![Named Range Reference](/images/excel-data-validation-named-range-ref.png)

And this works exactly as you would expect.

| Reference Table                                                   |     | Data Validation Output                                         |
| ----------------------------------------------------------------- | --- | -------------------------------------------------------------- |
| ![Small Data](/images/excel-data-validation-table-small-data.png) |     | ![Small Result](/images/excel-data-validation-table-small.png) |
| ![Large Data](/images/excel-data-validation-table-large-data.png) |     | ![Large Result](/images/excel-data-validation-table-large.png) |

## Summary

Excel's Data Validation is a powerful solution to improving data entry and usability in your workbooks, however, it can be complicated to set everything up so allow new values to be added easily. Excel's newer dynamic functions like `TRIMRANGE` can help this but they still leave some usability limitations. Using Excel tables is a great solution that maintains ease of use but they cannot be used directly within the Data Validation feature. To workaround this, you can create a Named Range that using the dynamic table reference syntax and then use this directly as the source for your data validation.
