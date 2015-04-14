## set_font ##

```python
fpdf.set_font(family, style = '', size = 0)
```

### Description ###

Sets the font used to print character strings. It is mandatory to call this method at least once before printing text or the resulting document would not be valid.

The font can be either a standard one or a font added via the [add_font](add_font.md) method. Standard fonts use Windows encoding cp1252 (Western Europe).

The method can be called before the first page is created and the font is retained from page to page.

If you just wish to change the current font size, it is simpler to call [set_font_size](set_font_size.md).

**Note**: the font metric files must be accessible. They are searched successively in:

 * The directory defined by the FPDF\_FONTPATH constant (if this constant is defined)
 * The font directory located in the directory containing fpdf.py (if it exists)

### Parameters ###

family:
> Font family. It can be either a name defined by [add_font](add_font.md) or one of the standard families (case insensitive):
>>  * Courier (fixed-width)
>>  * Helvetica or Arial (synonymous; sans serif)
>>  * Times (serif)
>>  * Symbol (symbolic)
>>  * ZapfDingbats (symbolic)
> 
> It is also possible to pass an empty string. In that case, the current family is retained.

style:
> Font style. Possible values are (case insensitive):
>>  * empty string: regular
>>  * B: bold
>>  * I: italic
>>  * U: underline
> 
> or any combination. The default value is regular. Bold and italic styles do not apply to Symbol and ZapfDingbats.

size:
> Font size in points.
> The default value is the current size. If no size has been specified since the beginning of the document, the value taken is 12.

### Example ###

```python
# Times regular 12
pdf.set_font('Times')
# Arial bold 14
pdf.set_font('Arial', 'B', 14)
# Removes bold
pdf.set_font('')
# Times bold, italic and underlined 14
pdf.set_font('Times', 'BIU')
```

### See also ###

[add_font](add_font.md), [set_font_size](set_font_size.md), [cell](cell.md), [multi_cell](multi_cell.md), [write](write.md), [set_stretching](set_stretching.md).
