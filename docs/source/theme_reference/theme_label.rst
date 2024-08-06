.. _theme-label:

UILabel Theming Parameters
==========================

The :class:`UILabel <pygame_gui.elements.UILabel>` theming block id is 'label'.

Colours
-------

.. figure:: ../_static/label_colour_parameters.png

   A diagram of which part of the element is themed by which colour parameter. The text shadow **cannot** be themed
   with a colour gradient.

:class:`UILabel <pygame_gui.elements.UILabel>` makes use of these colour parameters in a 'colours' block. Most of these colours can
also be a colour gradient:

 - "**dark_bg**" - The background colour/gradient of the label text.
 - "**normal_text**" - The colour/gradient of the text itself.
 - "**disabled_text**" - The colour/gradient of the text when the label has been disabled.
 - "**text_shadow**" - The colour of the shadow behind the text, if any exists.

Font
-----

:class:`UILabel <pygame_gui.elements.UILabel>` accepts a font specified in the theme via a 'font' block. A 'font' block has these parameters:

 - "**name**" - Necessary to make a valid block. This is the name that this font goes by in the UI, if this is a new font then subsequent font instances with different styles or sizes should use the same name.
 - "**locale**" - Optional parameter to set this font as belonging to a particular locale only. See the :ref:`localization` guide. You will need to keep repeating the locale specifier if using prototypes to make a hierarchy.
 - "**size**" - Necessary to make a valid block. This is the point size of the font to use on the label.
 - "**bold**" - Optional parameter. Set it to "1" to make this font bold.
 - "**italic**" - Optional parameter. Set it to "1" to make this font italic.

There are two methods to refer to font resource locations. First, using packaged resources:

 - "**regular_resource** - The location of this font's file with no particular style applied.
    - **package** - The name of the python package containing this resource - e.g. 'data.fonts'
    - **resource** - The file name of the resource - e.g. 'FiraCode-Regular.ttf'
 - "**bold_resource**" - The location of this font's file with bold style applied.
    - **package** - The name of the python package containing this resource - e.g. 'data.fonts'
    - **resource** - The file name of the resource - e.g. 'FiraCode-Bold.ttf'
 - "**italic_resource**" - The location of this font's file with italic style applied.
    - **package** - The name of the python package containing this resource - e.g. 'data.fonts'
    - **resource** - The file name of the resource - e.g. 'FiraMono-Italic.ttf'
 - "**bold_italic_resource**" - The location of this font's file with bold and italic style applied.
    - **package** - The name of the python package containing this resource - e.g. 'data.fonts'
    - **resource** - The file name of the resource - e.g. 'FiraMono-BoldItalic.ttf'

Second using paths:

 - "**regular_path**" - The path to this font's file with no particular style applied.
 - "**bold_path**" - The path to this font's file with bold style applied.
 - "**italic_path**" - The path to this font's file with italic style applied.
 - "**bold_italic_path**" - The path to this font's file with bold and italic style applied.

You only need to specify locations if this is the first use of this font name in the GUI.


Misc
-----

:class:`UILabel <pygame_gui.elements.UILabel>` has the following miscellaneous parameters in a 'misc' block:

 - "**text_shadow_size**" - The increased size in pixels of the shadow/outline. Set to "0", "1" or "2", larger than that the effect breaks down and individual letters merge together. Defaults to "0", no shadow.
 - "**text_shadow_offset**" - Pixel offset in horizontal (x) and vertical (y) dimensions for where the shadow is drawn. In the format "x,y". Defaults to "0,0".
 - "**text_horiz_alignment**" - Set to "left", "right" or "center". Controls the horizontal placement of the label text. Default is "center".
 - "**text_vert_alignment**" - Set to "top", "bottom or "center". Controls the vertical placement of the label text. Default is "center".
 - "**text_horiz_alignment_padding**" - If horizontal alignment is set to 'left' or 'right' this value will control the buffer between the edge of the label rectangle and where we start placing the text. Default is "0".
 - "**text_vert_alignment_padding**" - If vertical alignment is set to 'top' or 'bottom' this value will control the buffer between the edge of the label rectangle and where we start placing the text. Default is "0".
 - "**tool_tip_delay**" - time in seconds before the button's tool tip (if it has one) will appear. Default is "1.0".

Example
-------

Here is an example of a label block in a JSON theme file using the parameters described above.

.. code-block:: json
   :caption: label.json
   :linenos:

    {
        "label":
        {
            "colours":
            {
                "dark_bg": "#25292e",
                "normal_text": "#c5cbd8",
                "text_shadow": "#505050"
            },
            "font":
            {
                "name": "montserrat",
                "size": "12",
                "bold": "0",
                "italic": "0"
            },
            "misc":
            {
                "text_shadow": "1",
                "text_shadow_size": "1",
                "text_shadow_offset": "0,0"
            }
        }
    }
