---
title: Making a research poster with inkscape, R and dia
author: Chris
date: '2019-08-25'
slug: making-a-research-poster-with-inkscape-r-and-dia
categories: [research, conference, poster]
tags:
  - Academic
image:
  caption: ''
  focal_point: ''
---

I recently made a poster for the [IAREP-SABE Conference 2019](https://iarep.ucd.ie/) and thought it would be useful to outline the process. The finished poster is [here](https://blog.christopherjwilson.uk/Poster_Final_cmyk.pdf). Not to suggest this poster is a perfect (or good) example, but some people might find this guide useful.

## Consdier using a vector graphics tool like Inkscape

Posters are usually printed in A0 or A1 size. This means that the graphics and text we see on a computer screen need to be scaled up when printing in large sizes. Conventional image formats such as .jpg or .png - known as raster graphics - are made up of pixels and scaling them up makes them blurry. Vector graphics, on the other hand, use geometry to create the image independently of resolution; so they look clear regardless of size [(see here for a quick explanation)](https://guides.lib.umich.edu/c.php?g=282942&p=1885352). 

[Inkscape](https://inkscape.org/) is a cross-platform vector graphics tool that is free and open-source. 

## Be aware of the printer's requirements

The printer that I used required a 10mm "bleed area" around all of the edges. This means that the image sent to them needs to be bigger than A0 and will be cut to size after it is printed. A0 dimensions are 841 x 1189 mm. Adding 10mm to top,bottom,left and right means the dimensions need to be 861 x 1209 mm, so to begin making the poster, I create a canvas with these dimensions. *File > Document > Properties > Page* It is also important to set the resolution to at least 300 dpi.

## Use font sizes that will be visible from a distance

Everyone has different preferences for the best font size. I would suggest 32pt as the smallest size for all main text areas. I used a lager size for headers (e.g. 48pt) and I did use a slighly smaller size for some less important areas (26pt). When adding text in inkscape, drag the box to the size you want it to be. Then, if you need to modify the layout of the text, use the text tool (looks like an "A") to resize the box, rather than the normal object dragging tool (looks like an arrow).

## Use guides to align everything correctly and manage space

Inkscape allows us to create a grid on the canvas so that we can align objects consistenly. To toggle the grid on and off, use the "#" key. I used the grids function to divide the canvas into 100 minor squares and 10 major squares (i.e. for a width of 841mm, place a square every 8.41mm). This makes organising content easier: *File > Document Properties > Grids*. Using the grids, you can decide what distance you will have between sections, paragraphs, diagrams etc. It is also a good idea to use the align tool to line up content exactly: *Objects > Align and Distribute*

## Importing other graphics 

I used ggplot to make one of my plots in R. When exporting the png, it is a good idea to increase the resolution to that it looks okay when printed (remember, png is a raster format, so we're trying to use images that are at least 300 dpi). I increased my plot resolution 4x larger than its original size, while maintaining the aspect ratio. This seemed to look fine. 

Finding a high resolution university logo that also had transparency was not as easy. If you can get a vector format (e.g. svg or pdf) then that would be preferable.

## Creating diagrams with DIA and GraphViz

The main diagram on my poster outlines the experimental design and procedure. I usually use [dia](http://dia-installer.de/) for these type of diagrams. It has the ability to export to many image formats.

I also create some diagrams in RStudio with GraphViz code. This can be done in a number of ways. I first came across this approach using [DiagrammeR](https://rich-iannone.github.io/DiagrammeR/). A benefit of this approach is that, if you use R, then the values that go into the diagram can be entered programmatically.

## Working with colours

The colours that I used in my poster were based on the University's branding. To get the right colours, I used [ColorZilla](https://www.colorzilla.com/) in my web browser to select the colours from the university website. I then used [coolors](https://coolors.co) to create a colour pallete that fit around the main brand colours and used these in Inkscape.

## Preparing for printing

To get the poster from Inkscape to the printer, save the file as a pdf. *File > Save a copy*. During the process:

 - save the text as paths  
 - set the raster resolution to 300 dpi

Another preparation step is to set the colour profile to one that the printer uses. Inkscape creates images using RGB, whereas printers use CMYK. It is possible to convert colour profiles in PDFs using [ghostscript](https://www.ghostscript.com/). Once installed, the following batch script will convert the file from RGB to CMYK (on windows computers): 

    @echo off
    
    "C:\Program Files\gs\gs9.27\bin\gswin64c.exe" -dsafer -dBATCH -dNOPAUSE -dNOCACHE -sDEVICE=pdfwrite -sColorConversionStrategy=CMYK -dProcessColorModel=/DeviceCMYK -sOutputFile=%2 %1
    
    ECHO Congratulations! Your first batch file executed successfully.
    PAUSE


To use, save in a text file with the .bat extension (e.g. "converer.bat"), in the same folder as your pdf. Call the script in the command line with the first argument as your original file and the second as the name you want for the new file:

    converter.bat original_poster.pdf new_poster.pdf

The poster will be converted to a colour profile that is ready for printing!








