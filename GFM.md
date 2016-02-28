#GFM

### Quick links

```
- [Headings](#headings)
- [Styling text](#styling-text)
    - [Test](#test)
```
- [Headings](#headings)
- [Styling text](#styling-text)
    - [Test](#test)

## Headings

# The largest heading
## The 2nd largest heading
### The 3rd largest heading
#### The 4th largest heading
##### The 5th largest heading
###### The smallest heading (6#)

## Styling text

Bold	`** **` or `__ __`	command/control + b	**This is bold text**

Italic	`* *` or `_ _`	command/control + i	*This text is italicized*

Strikethrough	`~~ ~~`		~~This was mistaken text~~

Bold and italic	`** **` and `_ _`		**This text is _extremely_ important**

#### Test

##Wrapping to the next row

Press ENTER 2 times after the end of the line.  
Insert a blank line.(Use 2 spaces after the end of the line, then press ENTER.)  
Use \<br> to wrap to the next row.  
```
111
111

111
```
111
111

111
```
111  //2 spaces
111
```
111  
111
```
111<br>111
```
111<br>111

## Quoting text

In the words of Abraham Lincoln:
> Pardon my French
<br><br><br>
> Coffee. The finest organic suspension ever devised... I beat the Borg with it.- Captain Janeway

## Quoting code

Use `git status` to list all new or modified files that haven't yet been committed.

Some basic Git commands are:
```
git status
git add
git commit
```

```
function test() {
  console.log("notice the blank line before this function?");
}
```

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

## Links

`command + k`

This site was built using [GitHub Pages](https://pages.github.com/).

[GitHub Pages](http://blog.csdn.net/guodongxiaren "悬停显示")  

Visit https://github.com

## Linking to a file in the local repository

`[Book](./Book)`  
[Book](./Book)

`[GFM](./GFM.md)`  
[GFM](./GFM.md)

## Anchors

Use the anchor tag `#` in HTML to define where we want to jump to.  
Please note that the words in parentheses should be lowercase.

`[Headings](#headings)`
[Headings](#headings)

## Images

![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)


## Lists

use `-` or `*`. Don't miss the space after `-` or `*`.

```
- George Washington
- John Adams
- Thomas Jefferson
```
- George Washington
- John Adams
- Thomas Jefferson
```
* George Washington
* John Adams
* Thomas Jefferson
```
* George Washington
* John Adams
* Thomas Jefferson
```
1. James Madison
2. James Monroe
3. John Quincy Adams
```
1. James Madison
2. James Monroe
3. John Quincy Adams
```
- Dashes work just as well
- And if you have sub points, put two spaces before the dash or star:
  - Like this
  - And this
```
- Dashes work just as well
- And if you have sub points, put two spaces before the dash or star:
  - Like this
  - And this
```
1. Item 1
2. Item 2
3. Item 3
   * Item 3a
   * Item 3b
```
1. Item 1
2. Item 2
3. Item 3
   * Item 3a
   * Item 3b
```
1. Make my changes
  1. Fix bug
  2. Improve formatting
    * Make the headings bigger
2. Push my commits to GitHub
3. Open a pull request
  * Describe my changes
  * Mention all the members of my team
    * Ask for feedback
```
1. Make my changes
  1. Fix bug
  2. Improve formatting
    * Make the headings bigger
2. Push my commits to GitHub
3. Open a pull request
  * Describe my changes
  * Mention all the members of my team
    * Ask for feedback

## Task lists

```
- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request
```
- [x] Finish my changes
- [ ] Push my commits to GitHub
- [ ] Open a pull request
```
- [ ] a task list item
- [ ] list syntax required
- [ ] normal **formatting**, @mentions, #1234 refs
- [ ] incomplete
- [x] completed
```
- [ ] a task list item
- [ ] list syntax required
- [ ] normal **formatting**, @mentions, #1234 refs
- [ ] incomplete
- [x] completed

## Mentioning users and teams

@github/support What do you think about these updates?

## Using emoji

`:EMOJICODE:`

@octocat :+1: This PR looks great - it's ready to merge! :shipit:

For a full list of available emoji and codes, check out [emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com/).

## Paragraphs and line breaks

You can create a new paragraph by leaving a blank line between lines of text.

## Ignoring Markdown formatting

You can tell GitHub to ignore (or escape) Markdown formatting by using `\` before the Markdown character.

Let's rename \*our-new-project\* to \*our-old-project\*.

## Creating a table

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

Cells can vary in width and do not need to be perfectly aligned within columns. There must be at least `three hyphens` in each column of the header row.

| Command | Description |
| --- | --- |
| git status | List all new or modified files |
| git diff | Show file differences that haven't been staged |

## Formatting content within your table

| Command | Description |
| --- | --- |
| `git status` | List all *new or modified* files |
| `git diff` | Show file differences that **haven't been** staged |

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |

To include a pipe | as content within your cell, use a \ before the pipe:

| Name     | Character |
| ---      | ---       |
| Backtick | `         |
| Pipe     | \|        |
