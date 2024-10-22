<head>
    <style>
        body {
            font-family: Courier;
            # background-color: white;
            # color: black
        }
        #ex_heading {
            margin-left: 10px;
            border-bottom: 0.2px solid gray;
        }
    </style>

</head>


# Blog Guide

This file serves as a guide to the blog's functions and rules

[Here to stop drafts folder from disappearing]

<a href="https://docs.google.com/document/d/1gA2eBKCtSg0oXs_ZoYT_jtb-ClJofTeQS77e2w4IIH0/edit?usp=sharing">Guide Doc</a>

## Folder Notes

All blog posts should be put in the “_posts” folder

Empty folders will be erased as Github deals more with files than folder

**Note:** Folder names should begin with an underscore (_) and no space between the title (Ex. _posts)
- With some exceptions (i.e. the image folder)

## File Naming Rules

Files should be named:
- **Date**
- Year-Month-Day | Ex. 2024-09-13
    - Always include double digits in month and day
    - Separate from title using dash 
    - If the date in the title has not passed yet the post will not show up
- **Title of post**
    - my-blog-title
    - Keep it short, separate words by dashes
    - Ending with “.md”
    - The title in file will show up on homepage
- **All together:** 2024-09-13-my-blog-title.md 

## Formatting

Title of the post goes in line 1 and since it is a heading you put a hashtag (#) in front of it with space in between the title and the hashtag.

    # Title of post

Headings for sections (or subheadings) of text have 2 hashtags (also with space in between it and the title).

    ## Title for section of post

Headings also have divider lines underneath them.
	
<p id="ex_heading">Heading</p>

To include code in its own box:

‘’’coding language

[Insert Code Here] 

‘’’

HTML can be used in markdown files in order to add elements in a particular fashion, i.e. smaller texts for images/code, links, etc.

## Text Styles

In order to bold text put two asterisks (** **) on either side of the text you want to bold without spaces.

** bold ** 

**Link to Markdown Style Guide:** https://www.markdownguide.org/cheat-sheet/

As previously stated, text can also be changed in larger ways by using HTML (specifically the <\p> or paragraph tag).

As text can be changed within the <\p> tag using the style attribute, it can be changed the same way.

## Images

Images must be added using HTML (use <\img> tag) 

The src attribute value should be “/blog/images(or folder images are in)/name of image file” 
