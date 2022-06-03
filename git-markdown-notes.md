# BASIC formating on GitHub markdown file <!-- omit from toc -->

**Table of Contents**
- [BASIC formating on GitHub markdown file](#basic-formating-on-github-markdown-file)
  - [Headings](#headings)
  - [Styling text](#styling-text)
  - [Quoting](#quoting)
      - [Quoting text](#quoting-text)
      - [Quoting code](#quoting-code)
  - [Links](#links)
    - [Section links](#section-links)
    - [Relative links](#relative-links)
  - [Lists](#lists)
    - [Nested Lists](#nested-lists)
  - [Using emoji](#using-emoji)
  - [Paragraphs](#paragraphs)
  - [Footnotes](#footnotes)
  - [Hiding content with comments](#hiding-content-with-comments)
  - [Ignoring Markdown formatting](#ignoring-markdown-formatting)
  - [Creating a collapsed section](#creating-a-collapsed-section)
  - [References](#references)

## Headings
  Six levels of heading determined by the number of preceeding **#**

  ````
  # Largest Heading <!-- omit from toc -->
  ## Second largest Heading <!-- omit from toc -->
  ###### Smallest Heading <!-- omit from toc -->
  ````   
   
## Styling text

You can set text style of bold, italic, subscript, or superscript.

|Style	|Syntax	|Keyboard shortcut	|Example	|Output|
|---|---|---|---|---|
|Bold	|** ** or __ __	|Ctrl+B (Windows/Linux)	|\*\*This is bold text\*\*	|**This is bold text**|
|Italic	|* * or _ _     	|Ctrl+I (Windows/Linux)	|\*This text is italicized\*	|*This text is italicized*|
|Subscript	|\<sub> \</sub>		||\<sub>This is a subscript text\</sub>	|<sub>This is a subscript text</sub>|
|Superscript	|\<sup> \</sup>		||\<sup>This is a superscript text\</sup>	|<sup>This is a superscript text|
   
     
## Quoting 

  #### Quoting text
  
  Text that is not a quote

  > Text that is a quote
  
  <br>
  
  #### Quoting code
  
  Single backticks ( **\` \`** ) is used for inline quoting. Keyboard shortcut: `Ctrl` + `E`
  
  **Example:** Use `git init` to initiate a git repository    

  <br>
  
  Use triple backticks ( **\`\`\` \`\`\`** ) for its own distinct block of code.
  
  **Example:**
  
  ````
  ```
  git int
  git add
  git commit
  ```
  ````
  
  ```
  git int
  git add
  git commit
  ```   
   
## Links
  
  > You can create an inline link by wrapping link text in brackets `[ ]`, and then wrapping the URL in parentheses `( `). You can also use the keyboard shortcut `Command+K` to create a link. When you have text selected, you can paste a URL from your clipboard to automatically create a link from the selection.
  
  Putting direct link also work:
  
  This site was built using \[GitHub Pages\](https://pages.github.com/)
  
  This site was built using [GitHub Pages](https://pages.github.com/)
  
  <br/>

  ### Section links
  You can link directly to a section in a rendered file by hovering over the section heading to expose [right click and copy] the link:
  
  [Click to go Section Lists](#lists)
  
  ### Relative links
  A relative link is a link that is relative to the current file and help readers navigate to other files in your repository.

  > For example, if you have a README file in root of your repository, and you have another file in docs/CONTRIBUTING.md, the relative link to CONTRIBUTING.md in your README might look like this:

  ````
  [Contribution guidelines for this project](docs/CONTRIBUTING.md)
  ````
  
## Lists
  
Make an **unordered list** by preceding one or more lines of text with `-` or `*`.

````
- item 01
- item 02
- item 03
````
  
* item 01
* item 02
* item 03
  

To order your list, precede each line with a number.

````
1. item 01
2. item 02
3. item 03
````
  
1. item 01
2. item 02
3. item 03
  
### Nested Lists
  
You can create a nested list by indenting one or more list items below another item. Type space characters in front of your nested list item, until the list marker character (`-` or `*`) lies directly below the first character of the text in the item above it.
  
````
1. First list item
   - First nested list item
     - Second nested list item
  
````
1. First list item
   - First nested list item
     - Second nested list item
  
  
  
## Using emoji
> You can add emoji to your writing by typing `:EMOJICODE:`.
````
@octocat :+1: This PR looks great - it's ready to merge! :shipit:
````
Rendered emoji
@octocat :+1: This PR looks great - it's ready to merge! :shipit:
  
Typing `:` will bring up a list of suggested emoji. The list will filter as you type, so once you find the emoji you're looking for, press **Tab** or **Enter** to complete the highlighted result.
  
  
## Paragraphs
> You can create a new paragraph by leaving a blank line between lines of text.
  
  
## Footnotes
> You can add footnotes to your content by using this bracket syntax:
  
````
Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].  

You can also use words, to fit your writing style more closely[^note].

[^1]: My reference.
[^2]: Every new line should be prefixed with 2 spaces.  
  This allows you to have a footnote with multiple lines.
[^note]:
    Named footnotes will still render with numbers instead of the text but allow easier identification and linking.  
    This footnote also has been made with a different syntax using 4 spaces for new lines.
````

Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].  

You can also use words, to fit your writing style more closely[^note].

[^1]: My reference.
[^2]: Every new line should be prefixed with 2 spaces.  
  This allows you to have a footnote with multiple lines.
[^note]:
    Named footnotes will still render with numbers instead of the text but allow easier identification and linking.  
    This footnote also has been made with a different syntax using 4 spaces for new lines.
  
## Hiding content with comments
> You can tell GitHub to hide content from the rendered Markdown by placing the content in an HTML comment.
````
<!-- This content will not appear in the rendered Markdown -->
````
<!-- This content will not appear in the rendered Markdown -->

## Ignoring Markdown formatting
> You can tell GitHub to ignore (or escape) Markdown formatting by using \ before the Markdown character.
````
Let's rename \*our-new-project\* to \*our-old-project\*.
````
Let's rename \*our-new-project\* to \*our-old-project\*.

## Creating a collapsed section
  
Any Markdown within the `<details>` block will be collapsed until the reader clicks ▶️ to expand the details. Within the `<details>` block, use the `<summary>` tag to create a label to the right of ▶️

````
<details><summary>CLICK ME</summary>

#### We can hide anything, even code! <!-- omit from toc -->

    ```python
      print("Hello World")
    ```
</details>
````
  
<details><summary>CLICK ME</summary>

#### We can hide anything, even code! <!-- omit from toc -->

    ```python
      print("Hello World")
    ```


</details>
  
  
## References

[GitHub Docs: Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

[Organizing information with collapsed sections](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-collapsed-sections)
  
[Markdown Support for Visual Studio Code](https://github.com/yzhang-gh/vscode-markdown)
