# trilium-linen-theme
Linen is a minimal, airy light theme for Trilium with an optional distraction-free mode.

Design principles
-----------------

Partly inspired by Edward Tufte's [visual style](https://edwardtufte.github.io/tufte-css/), Linen is guided by the following choices:

*   Using white space and the proximity principle to focus on the content and make the interface less cluttered. 
*   Muted, slightly off-white backgrounds to avoid an aggresive contrast, but trying to keep text, links and selected notes distinct.
*   A legible, elegant serif font for content (Crimson Pro) and a compact, minimal font for menus and organization (Roboto Condensed)
*   Images are first-class citizens, especially in grid mode
*   An optional distraction-free mode (you need to create a button for it to work)

Screenshots
-----------
![note](Screenshots/trilium-linen-theme-note.png)

A note with images:
![image grid](Screenshots/trilium-linen-theme-image-grid.png)

Zen mode:
![note](Screenshots/trilium-linen-theme-zen-mode.png)

Disclaimer
----------

I'm a CSS amateur. Please create an issue if you encounter any problems, I will do my best to solve them.

Usage
-----

The theme should work with Trilium version 0.49.5+

1.  Create a CSS code note in Trilium and name it `Linen`
2.  Paste the content from `Linen.css` in it
3.  Add the `#appTheme=Linen` attribute to it
4.  Download all the fonts in Fonts, then right-click on the note and select Import to note
5.  Add the attribute `#customResourceProvider=font-name.woff2` to each font
6.  Go to Menu > Options, and select Linen as your new theme
7.  Ctrl + R to reload

Distraction-free mode
---------------------

Linen has an optional distraction-free (zen) mode, which hides the launcher pane, the left pane, the note tabs and the window controls at the click of a button or using a keyboard shortcut. To keep any of those elements, go to the bottom of the CSS page and comment out or delete the relevant section.  The ribbon and the new split button are still visible by default, but you can uncomment the two relevant sections in the CSS file to have only the content visible on the screen.

This works **only** if you create the button to activate distraction free mode. To create the button:

1.  Create a new note,  type JS Frontend
2.  Add the following code:
```
    api.addButtonToToolbar({
        title: 'Zen mode',
        icon: 'spa',
        action: function() {
             $("body").toggleClass("zen-mode");
        },
        shortcut: 'alt+t'
    }); 
```
3. Add the attribute `#run=frontendStartup` 
4. (optional) Change the icon to whatever make sense to you. The same with the keyboard shortcut (in the code snippet above it uses Alt + t, I used Alt+z because it makes more sense mnemonically, but it is already used by the app for opening a note in an external editor, so I had to change that shortcut in Options.)
5. **!Important!** - zen mode can be toggled off only with the keyboard shortcut.

Thank you
-----------

* Zadam, for creating this marvelous note-taking tool and for advice on how to implement zen-mode [here](https://github.com/zadam/trilium/issues/2572#issuecomment-1014906331).
* Bert010 for his beautiful [cleantype theme](https://github.com/bert010/trilium-theme), from which I borrowed liberally on how images are displayed.
