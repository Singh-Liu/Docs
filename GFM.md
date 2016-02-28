#GFM

[TOC]

### Quick links
- [Headings](##Headings)
- [Styling text](##Styling text)
- 


##Headings


# The largest heading
## The 2nd largest heading
### The 3rd largest heading
#### The 4th largest heading
##### The 5th largest heading
###### The smallest heading (6#)

##Styling text

Bold	|** **| or |__ __|	command/control + b	**This is bold text**

Italic	* * or _ _	command/control + i	*This text is italicized*

Strikethrough	~~ ~~		~~This was mistaken text~~

Bold and italic	** ** and _ _		**This text is _extremely_ important**

##Quoting text

In the words of Abraham Lincoln:
> Pardon my French

##Quoting code

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

##Links

`command + k`

This site was built using [GitHub Pages](https://pages.github.com/).

Visit https://github.com

##Lists

use `-` or `*`

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

##Task lists

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

##Mentioning users and teams

@github/support What do you think about these updates?

##Using emoji

`:EMOJICODE:`

@octocat :+1: This PR looks great - it's ready to merge! :shipit:

##Paragraphs and line breaks

You can create a new paragraph by leaving a blank line between lines of text.

##Ignoring Markdown formatting

You can tell GitHub to ignore (or escape) Markdown formatting by using `\` before the Markdown character.

Let's rename \*our-new-project\* to \*our-old-project\*.

##Creating a table

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

Cells can vary in width and do not need to be perfectly aligned within columns. There must be at least `three hyphens` in each column of the header row.

| Command | Description |
| --- | --- |
| git status | List all new or modified files |
| git diff | Show file differences that haven't been staged |

##Formatting content within your table

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
