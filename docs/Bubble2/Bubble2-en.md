---
marp: true
theme: default
size: 16:9
header: ''

page_number: true
paginate: true
---

Programming Boot Camp Learning Phase #4

# Bubble Basic #2-1

2022/11/26

---

## Advance preparation

- Today we will add design and logic to the pet health management app we created last time.
- Since we have made some modifications for today's lecture, we will ask you to use a copy of the application prepared by us in order to match the starting point.
- We will distribute the duplicated application, so please send the e-mail address where you created your Bubble account to `@Naotake KYOGOKU`.
![w:500px](images/2022-11-24-08-51-37.png)

---

## Things to do today

  - Review of last time
  - Craft your design
  - Create logic

---

## Review of last time

- [Bubble](https://bubble.io/) is a visual programming tool, and it is a tool that allows you to program the appearance and movement by operating from the screen.
- It is a web application premise, and it will be compatible with smartphones and PCs by adjusting the display size.

- If you were absent last time, let's catch up with this material
  - https://github.com/GuildWorks/titech-2022/tree/master/docs/Bubble1

---

## Review of last time

The pet registration, list, details, and weight record screens of the pet management application
While making it, I learned how to use Design/Workflow/Data, which are the basics of Bubble.

![w:800](images/2022-11-25-09-05-41.png)

---

## Things to do today

This time, we will further add design and logic to the previous application.

---

### This is what the end looks like

top page

![w:700](images/2022-11-26-02-50-05.png)![w:350](images/2022-11-26-02-50-24.png)

---

pet list

![w:700](images/2022-11-26-02-51-38.png)![w:300](images/2022-11-26-02-51-20.png)

---

pet details

![w:700](images/2022-11-26-02-52-36.png)![w:300](images/2022-11-26-02-52-54.png)

---

Advisor pet list

![w:900](images/2022-11-26-02-57-34.png)

---

### Now let's get started.
### First, we will create the design

---

### What to do in the design process

- Let's create a screen that fits the display size
  - Uses a technique called responsive web design to control the look to the display size
- Let's use Style
  - Edit and add styles, or apply styles individually

---

## Create a screen that fits the display size

---

## Create a screen that fits the display size

- Web applications are used on various terminals such as PCs, tablets, and smartphones.
- The display size is different for each terminal, but there is a design method called responsive web design as a method to deal with them.
- Depending on the screen size, it is a method that flexibly switches the appearance of elements such as expanding/shrinking, wrapping/not wrapping, and displaying/not displaying.
- As a method of implementation, specify rules for determining placement and size, rather than specifying fixed placement and size.
- By default, Bubble has a fixed placement and size, but you can also specify various rules.

---

## Commonly used rules

In order to achieve responsive design with Bubble, there are the following rules that are often used.

1. Placement rules within parent elements
2. Element sizing rules
3. Display presence/absence rules

Combine these rules to achieve responsive screen design.
It should be noted that these rules are not limited to Bubble, but also apply to web applications in general.

Later, we will incorporate it into the screen together, but some ideas are difficult, so I will explain the outline first.

---

## Rule 1: Placement rules within parent elements

It will be a rule specification for how to place it in the parent element.

In Bubble, a parent element that encloses a group such as a repeating group or an individual element such as an entire page is called a container.
A Container allows you to specify placement rules for the child elements it contains.

![w:600](images/2022-11-25-09-18-25.png)

---

There are four placement rules for child elements:

- Fixed: Specify a fixed placement location
- Align to parent: specify the position relative to the parent element
- Row: Arrange in row direction (horizontal direction)
- Column: Arrange in column direction (vertical direction)

I will explain step by step.

---

## Fixed: Specify a fixed placement location

This is a rule that specifies a fixed placement location. Specifies the placement location in pixels.
It will be the initial setting when the parent element is placed in Bubble.

Since it is specified as fixed, it will not change from the specified position even if the screen width is changed. In the example below, it extends off the screen.

![w:400](images/2022-11-25-07-40-30.png)→![w:120](images/2022-11-25-07-41-48.png)

---

## Align to parent: specify the position relative to the parent element

This is a rule that specifies the position relative to the parent element.
In Bubble, you can specify the placement location from 9 areas.
![](images/2022-11-25-07-46-27.png)

After changing the screen width, it moves while maintaining the relative position. In the example below, when the screen width is narrowed, it moves while maintaining the relative positions of upper left, center, and lower right.
![w:500](images/2022-11-25-07-48-50.png)→![w:140](images/2022-11-25-07-50-08.png)

---

## Row: arrange in row direction (horizontal direction)

The rule is to arrange them in the row direction (horizontal direction). Lines are automatically wrapped.
In the example below, narrowing the screen width causes the lines to wrap, resulting in a vertical line.
![w:300](images/2022-11-25-07-56-45.png)→![w:140](images/2022-11-25-07-57-06.png)

---

## Row: You can specify the horizontal (left and right) alignment in the row
You can specify the vertical alignment within the row for each element.
![w:600](images/2022-11-25-08-14-01.png)
![w:300](images/2022-11-25-08-14-33.png) (Left-aligned)
![w:300](images/2022-11-25-08-14-54.png) (Centered)
![w:300](images/2022-11-25-08-15-15.png) (Right-aligned)
![w:300](images/2022-11-25-08-16-46.png) (Space-around)
![w:300](images/2022-11-25-08-17-11.png) (Space-between)

---

## Row: You can specify the vertical (top and bottom) alignment in the row
You can specify vertical alignment within a row.
*This is specified for the child element, not the parent element.

![w:600](images/2022-11-25-08-10-28.png)
![w:300](images/2022-11-25-08-07-34.png)![w:300](images/2022-11-25-08-08-19.png)![w: 300](images/2022-11-25-08-08-49.png)

---

## Column: Arrange in column direction (vertical direction)

Arrange in columns (vertically).
In the example below, the images are aligned vertically in the left-right center alignment, and even if the screen width is reduced, they are aligned vertically while maintaining the center alignment.
![w:450](images/2022-11-25-08-29-13.png)→![w:130](images/2022-11-25-08-29-31.png)

Horizontal and vertical alignment can be specified in the same way as Row. (Contents that can be specified for horizontal and vertical are opposite)

---

## Rule 1 (Recap): Placement rules within parent elements

It will be a rule specification for how to place it in the parent element.
There are four placement rules for child elements:

- Fixed: Specify a fixed placement location
- Align to parent: specify the position relative to the parent element
- Row: Arrange in row direction (horizontal direction)
- Column: Arrange in column direction (vertical direction)

---

## Rule 2: Element Sizing Rule

Instead of specifying a fixed size so that it can grow or shrink depending on the screen width, specify rules for determining its size. Mainly use one of the following two.
- specify a percentage of the size of the parent element
- Specify maximum/minimum size when stretched/shrinked
  - *It is also possible to set unlimited without specifying the maximum and minimum

---

## Percent specification

The example below specifies that the width is 80% of the screen. Reducing the screen width also reduces the image size while maintaining the 80% percentage.

![w:600](images/2022-11-25-08-43-41.png)→![w:180](images/2022-11-25-08-44-19.png)

---

The example below specifies a maximum width of 800px and a minimum width of 300px.
It expands and contracts between 300px and 800px, but even if the screen is widened, it will not be larger than 800px, and conversely, even if the screen is narrowed, it will not be smaller than 300px.

![w:600](images/2022-11-25-08-49-25.png)→![w:150](images/2022-11-25-08-50-59.png)

---

## Rule 3: Visibility rule

You can switch between showing and hiding elements on the screen by specifying the lower and upper limits of the screen width.

The example below specifies that the image will not be displayed when the screen width is 800px or less.
![w:600](images/2022-11-25-09-02-33.png)→![w:170](images/2022-11-25-09-03-22.png)

It is often used when you want to display a lot of information only when the screen is large.

---

## Frequently used rules (review)

In order to achieve responsive design with Bubble, there are the following rules that are often used.

1. Placement rules within parent elements
2. Element sizing rules
3. Display presence/absence rules

Let's actually use it.

---

## (reconfirmation) advance preparation

- Today we will add design and logic to the pet health management app we created last time.
- Since we have made some modifications for today's lecture, we will ask you to use a copy of the application prepared by us in order to align the starting points.
- We will distribute the duplicated application, so please send the e-mail address where you created your Bubble account to `@Naotake KYOGOKU`.

![w:500px](images/2021-11-17-05-35-39.png)

---

## Apply responsive design to top page (login page)
First, apply a responsive design to the top page (login page).
Before support, the login area was only visible in the corner when displayed on a smartphone.
When supported, it will be displayed in the center according to the screen width.
![w:200](images/2022-11-25-09-54-55.png)→![w:210](images/2022-11-25-10-22-24.png)

Use Align to parent, which was introduced as a placement rule within the parent element.

---

Open the top page (login page). Do you remember the steps?
- Open `Design` in the menu on the left of the screen.
- Click on the right of the b logo on the top left of the screen and select the index page.
![bg right w:600](images/2022-11-25-09-52-58.png)

---

Double-click on a blank area of ​​the screen to open the settings window for the page itself.

![](images/2022-11-25-10-03-17.png)

---

- A settings window titled `index` should open.
- Open the tab called `Layout`
  - When opened, `Container layout` is set to `Fixed`.
  - This is the state of the fixed placement rule.
  - I'm going to change this.

![bg right w:600](images/2022-11-25-10-04-19.png)

---

Change the `Container layout` from `Fixed` to `Align to parent`
- Now the parent element (here the index page itself) has specified the rule that child elements should be positioned relative to each other.
![bg right w:600](images/2022-11-25-10-09-32.png)

---

Next, open the `Login Form` setting window.
- Click around the outer frame of the login form
  - If you move the mouse, some frames will appear, but the outer one will be the one.
- Make sure the window title is `Login Form`. Since the elements are nested, be careful not to open the setting window of another element.

![bg right w:600](images/2022-11-25-10-14-39.png)

---

Center.
- Open the `Layout` tab in the `Login Form` settings window
- Select the center where the placement positions are lined up.
![bg right w:400](images/2022-11-25-10-20-11.png)

---

If you can specify it, let's check it in the preview.
Even if you reduce the width of the browser, it should now be centered on the screen.

Now you know how to use Align to parent, which was introduced as a placement rule within the parent element.

![bg right w:300](images/2022-11-25-10-21-37.png)

---

## Apply responsive design to pet list page
Now it's time to apply a responsive design to the pet list page.
If it corresponds, the number of columns will change flexibly to the width of the screen, and you can see all pets in a list.
![w:210](images/2022-11-25-12-57-34.png)→![w:190](images/2022-11-25-19-43-10.png)

Use Column, which was introduced as a placement rule within the parent element.
We will also combine the size specification and responsive settings specific to the repeating group.

---

Let's change the `Container layout` of the page in the same way as the login page.
This time, specify `Column`.
- Open `pet_list` screen
- Double click on a blank part of the page to open the settings window for the page itself
- Specify Layout tab of setting window
- Change `Container layout` to `Column`

![bg right w:400](images/2022-11-25-13-04-53.png)

---

By doing so, the elements on the screen are arbitrarily arranged vertically.
Child elements directly under the parent element set by `Column` are arranged in the column direction (vertical direction). We will use this arrangement as a base.
![w:500](images/2022-11-25-13-07-22.png)

---

Next, we will set the repeating group.
- Open the setting window of the repeating group `pet list` and go to the `Layout` tab
- Enter the following settings
  - Horizontal alignment: `centered`

![w:600](images/2022-11-25-13-19-40.png)

The elements directly under the pet list page are arranged in columns, but at that time, this repeating group will be aligned horizontally and centered.

---

Additionally, set the following
  - Make this element fixed-widtht: unchecked
  - Min width: not specified
  - Max width: 1010px

This repeating group does not have a fixed width, but rather expands and contracts according to the width of its parent element (here the screen itself). However, if it spreads too much, it becomes difficult to see, so the maximum width is set to 1010px.

![bg right w:400](images/2022-11-25-13-48-42.png)

---

Enter the following settings
  - Make this element fixed-height: unchecked
  - Min height: not specified
  - Max height: Not specified (inf) * Probably an abbreviation for infinity
  - Fit height to content: checked

The height of this repeating group is not fixed, and it is set to expand and contract according to the contents.

![bg right w:400](images/2022-11-25-13-25-28.png)

---

Now let's show a preview.

It's still ugly, but the repeating group should be centered and stretch horizontally and vertically.

![w:600](images/2022-11-25-13-30-34.png)![w:150](images/2022-11-25-13-31-02.png)

However, the cell size is not the intended size, and the number of columns does not change. Let's set it up.

---

Now move to the `Appearance` tab of the repeating group's configuration window.
We will set the following.
- Set fixed number of rows: unchecked
-Min height of row: 200px
- Set fixed number of columns: unchecked
-Min width of column: 250px

The number of columns and rows is not fixed, and the minimum width of rows and columns is specified. This allows the number of rows and columns to be flexibly switched depending on the size of the table while maintaining the minimum width.

---

Now let's see the preview.

It's still ugly, but the number of columns and rows now changes according to the width of the screen and the width of the table.

![w:600](images/2022-11-25-18-40-10.png)![w:150](images/2022-11-25-18-41-08.png)

However, there are times when it's too far to the left in the cell, or when you reduce the width, you end up with an unintended margin. Let's fix it.

---


Also, go to the `Layout` tab in the Repeating Group's settings window.
Set the following:
- Cell's container layout: Align to parent

This is the setting used for the login page. Allows you to position elements relative to their parent element (here each cell of a repeating group).

![bg right w:400](images/2022-11-25-18-46-01.png)

---

Next, we will lay out the elements inside the cell.

Since the elements overlap and it is difficult to select, specify from the `Elements tree` on the left side of the screen.
- There is a section called `Elements tree` at the top of `UI Builder` in the Design menu.
- Uncheck `Only show hideable` if it is checked.
- *If only `pet list` is displayed, click `+` to open the tree.

![bg right w:400](images/2022-11-25-18-51-06.png)

---

Now, let's set it in order from `pet list image`.
- Click the `pet list image` in the `Elements tree` to open the settings window
- In the `Layout` tab, set the same as the image on the right.

It is set to be placed in the center of the cell and to be displayed as large as possible while maintaining the aspect ratio of 4:5.

![bg right w:400](images/2022-11-25-19-00-50.png)

---

Next, put the same settings as the image on the right in `Layout` of `Shape A`.

It is set to be placed at the bottom of the cell and displayed as large as possible to the left and right while maintaining the height of 45px.

![bg right w:400](images/2022-11-25-19-05-28.png)

---

Next, put the same settings as the image on the right in the `Layout` of `pet list name`.

It is the same content as `Shape A`.

![bg right w:400](images/2022-11-25-19-08-56.png)

---

Preview.

It's a shame. I'm also worried about the position and margins of the header.

![w:800](images/2022-11-25-19-09-40.png)![w:200](images/2022-11-25-19-10-45.png)

---

Open the header setting window and put the right setting in `Layout`.

Centered when lined up in columns on a page. The width is not fixed and extends up to 1080px according to the page width. Leave a 20px margin at the bottom. That's the setting.

![bg right w:350](images/2022-11-25-19-29-48.png)

---

## About Magin and Padding

Since the word "margin" is used for the first time, I will explain it.
There are two words for margins, Margin and Padding, which mean the following:
- Margin: Margin outside the bounds of the element
- Padding: padding inside the border of the element

![](images/2022-11-25-19-32-28.png)

Please be aware when you want to use different margins inside and outside the border.

---

Also, add some space to the repeating group.

Set the following in the `Layout` tab of the repeating group.

The top and bottom margins are 10px, and the left and right margins are 50px.

![bg right w:300](images/2022-11-25-19-38-36.png)

---

Now let's preview.

![w:800](images/2022-11-25-19-40-18.png)![w:250](images/2022-11-25-19-40-38.png)

Yay.
In addition, although the hamburger menu is displayed, please do not mind that it does not work.

---

### <Advanced>
## Apply responsive design to pet detail screen

Since the pet details screen cannot make use of the size of the PC screen, let's make it responsive.
Multi-column settings are made using the Row arrangement rule within the parent element.
It also controls the visibility of elements.

![w:400](images/2022-11-25-19-46-25.png)→![w:500](images/2022-11-25-23-12-02.png)

---

Combine the groups to create a column like this.
![w:800](images/2022-11-25-23-18-25.png)

---

I feel like this.

![w:700](images/2022-11-25-23-12-02.png)![w:300](images/2022-11-25-23-12-15.png)

---



First of all, we will create such a group.

![bg right w:450](images/2022-11-25-21-38-49.png)

---

We want to separate the image area and the text area, so create a group for each.

- Drag and select image label and image display part
- Right-click (or double-tap) to bring up the menu
- Specify `Group elements in a Fixed container`.

A group is created containing the selected elements. Since it is created as a fixed placement (Fixed) group, it will be a fixed placement within the group.

![bg right w:700](images/2022-11-25-19-53-13.png)

---

Similarly, drag the Name, Birthdate, and Gender elements to create a Fixed group.

![bg right w:500](images/2022-11-25-19-59-14.png)

---

Give the created group a name for easy identification later.
- Click a group from the `Elements tree` to bring up the settings window
- Click the title part of the setting window to change the name
  - `Group A` → `Image Group`
  - `Group B` → `Text Group`

![bg right w:700](images/2022-11-25-20-00-45.png)

---

Also, if the group and the element are exactly overlapping, it will be difficult to select the group later when you want to select it, so let's expand the group a little.
- Click a group from the `Elements tree` to bring up the settings window
- Drag the squares on the edges of the Group's elements to widen them

![bg right w:500](images/2022-11-25-20-12-33.png)

---

Next, since we want to create a column with image areas and text areas side by side, select `Image Group` and `Text Group` to create more groups.
- Select `Image Group` (I made it a little bigger so it's easier to select)
- Select `Text Group` while holding down Shift (two groups are selected)
- Right-click (or double-tap) to bring up the menu
- Specify `Group elements in a Row container`.
![bg right w:500](images/2022-11-25-20-25-56.png)

---

Let's spread it out a bit again so that it's easier to select the group later.

By specifying `Row` for the group, it becomes a group that arranges child elements in the row direction (horizontal direction).
Lines are automatically wrapped, and in the state created here, the width of the group is small, so it will be wrapped. If you widen the width enough to test, it will line up in the row direction.

![bg right w:500](images/2022-11-25-20-27-32.png)

---

We want to create a column so that the `Weight Logs` link and the `Back to list` link line up side by side, so we will create a group.
- Select the `Weight Logs` link
- Shift-select the `Back to list` link
- Right-click (or double-tap) to bring up the menu
- Specify `Group elements in a Row container`.
- Spread it out a little more

![bg right w:300](images/2022-11-25-21-32-34.png)

---

Give the created group a name for easy identification later.
- Click a group from the `Elements tree` to bring up the settings window
- Click the title part of the setting window to change the name
  - `Group C` → `Contents Group`
  - `Group D` → `Navigation Group`
![bg right w:700](images/2022-11-25-21-34-24.png)

---

I've created a lot of groups, and if all went well, they should look like the one on the right.

![bg right w:450](images/2022-11-25-21-38-49.png)

---

Specify the `pet_detail` page itself as the `Column`.
- Click an empty part of the screen to select `pet_detail`
- Open `Layout` tab
- Specify `Column` for `Container layout`

![bg right w:450](images/2022-11-25-21-43-42.png)

---

Then the elements should be aligned vertically by the left side.

By specifying `Column`, it is in a state of being aligned in the column direction.

![bg right w:400](images/2022-11-25-21-46-34.png)

---

Select the header (`header A`) and specify the Layout as shown on the right.

I understand what you mean by settings.
- When aligning in the column direction, align to the center with respect to the parent element
- Width expands and contracts up to 1100px to match the parent element.
- Leave a 20px margin on the bottom.
![bg right w:350](images/2022-11-25-21-51-47.png)

---

Select `Contents Area` and specify Layout as shown on the right.
You've got a new setting. It has the following meanings.
- When aligning in the row direction, the child elements (`Image Area` and `Text Area` here) should be centered.
- Use 40px line and column spacing between elements when aligning child elements.
- Align to the center when aligning in the column direction with respect to the parent element.
- The width expands and contracts according to the parent element.
![bg right w:350](images/2022-11-25-22-10-58.png)

---

Also specify margins.

![bg right w:350](images/2022-11-25-22-24-15.png)

---

Next, select `Navigation Area` and specify Layout as shown on the right.

It has the following meanings.
- Spread child elements horizontally when aligned horizontally.
- Align to the center when aligning in the column direction with respect to the parent element.
- Width expands and contracts according to the parent element.
- Vertical width stretches and shrinks according to the content.

![bg right w:350](images/2022-11-25-22-49-27.png)

---

Rearrange the positions of the `Back to list` and `Weight Logs` links.

- Select the `Back to list` link to open the settings window
- Open `Layout` tab
- Press the `Previous` button

In this way, you can change the sort order within the parent element specified by `Row` or `Column`. You can also change it by dragging, but this is easier to specify because it may be moved outside the group.

![bg right w:350](images/2022-11-25-22-28-41.png)

---

Similarly, rearrange the positions of the `Contents Group` and `Navigation Group`.

- Select the `Navigation Group` link to open the settings window
- Open `Layout` tab
- Press the `Previous` button

![bg right w:350](images/2022-11-25-22-33-34.png)

---

Let's preview.
I'm a little worried about the details, but I've created a multi-column layout.
Smartphones are arranged vertically.

![w:800](images/2022-11-25-22-38-11.png)![w:200](images/2022-11-25-22-38-57.png)

---

### <Excercexercises>

If you are concerned about the subtleties of the layout, try the following.
- Make the width of `Back to list` link and `Weight Logs` link expand and contract according to the content.
- Leave margins on the left and right of the `Navigation Area`.
- Increase image size and align text

---

I feel like this.

![w:750](images/2022-11-25-22-52-12.png)![w:300](images/2022-11-25-22-52-27.png)

---

## Next comes the weight graph

- On the pet_weight_register screen, click and copy the graph
- paste on pet_detail screen
- Press `Next` in `Layout` to place it at the bottom
- In addition, specify other items of `Layout` as shown in the right figure

![bg right w:350](images/2022-11-25-22-59-16.png)

---

It's cramped to display the graph on one screen on a smartphone, so when the screen width is small, it's not displayed.

- Open the graph settings window and open the `Conditional` tab
- Create a new condition and specify `Current page width`, `<`, `800` in `When`. It means that the current screen size is smaller than 800.
- Define what changes to make in that case. Select `This element is visible` and leave it unchecked

![bg right w:500](images/2022-11-25-23-07-53.png)

---

Let's preview.

![w:700](images/2022-11-25-23-12-02.png)![w:300](images/2022-11-25-23-12-15.png)

The graph is not displayed on the smartphone display.

---

## Frequently used rules (review)

In order to achieve responsive design with Bubble, there are the following rules that are often used.

1. Placement rules within parent elements
2. Element sizing rules
3. Display presence/absence rules

I combined these and applied a responsive design.

---

## Let's use Style

---

## Let's use Style

- Up until now, we've been using the styles that Bubble provides as standard.
- For the actual product, we draw and apply the design concept that matches the product.
- I will explain how to change the style from here

---

## There are three ways to apply Style

- Edit existing styles
- Apply styles individually
- add new styles

let's go in order

---

# edit an existing style

I would like to modify an existing style to change the color of buttons and links.

![w:800](images/2022-11-26-00-31-44.png)

---

## Let's use Style variables

Bubbles have their base colors and fonts set as `Style variables`.

Go to `Styles` in the left menu > `Style variables` in the tab at the top of the screen. The colors specified here can be used when creating or editing styles. For example, the Primary color setting is used by the Primary button.

![w:800](images/2022-11-26-00-23-44.png)

---

If you change the `Primary` setting in the `Style variables`, the change will be applied everywhere it is used.
- Select `Styles` on the left menu > `Style variables` on the tab at the top of the screen
- Change Primary. (I want dark red eyes, so I specify it with `#D62755`.)

![w:600](images/2022-11-26-00-15-38.png)

---

If you check the style of the Primary button, it has changed.

![w:800](images/2022-11-26-00-26-56.png)

---

Let's preview the screen.
The colors of the basic buttons and links, such as the login/logout buttons, have changed.

![w:800](images/2022-11-26-00-28-14.png)

---

## When to use Style variables

In this way, you can change the standard base color all at once by editing `Style variables`. Also, when creating or editing a new style, you can decide your own rules and use `Style variables` to make maintenance easier, such as batch changes later.

---

## Next, let's specify the style individually

I would like to match the header logo with the base color and make the font a little more cute.

![w:900](images/2021-11-20-02-10-35.png)

---

b Open the menu to the right of the logo and select Header

![](images/2021-11-20-01-57-35.png)


---

- Double click the logo to open settings
- Go to the `Style` part of the settings window
- Click `Remove style` in the lower right corner of the pull-down
  - Instead of applying the defined Style, you can specify it individually

![bg right w:500](images/2022-11-26-00-34-55.png)

---

specify the style you want
- I set the font color to the Primary color specified in the `Style variables`
- I like `Noto Serif Dogra` for the font, so I will specify it
- If you change the font, the logo may be cut off, so please adjust the width accordingly

![bg right w:500](images/2022-11-26-00-38-28.png)

---
## Let's preview

You've changed.

![w:800](images/2022-11-26-00-39-03.png)


---

## Now let's add a new style

The label is too big and I'm worried about it, so I'm going to create a style for the label.

![w:800](images/2022-11-26-00-46-25.png)

---

First, specify the style individually.

- Open pet_detail and double click on `Image` text to open settings
- Click `Remove style` at the bottom right of `Style` pull-down

![bg right w:600](images/2021-11-20-02-16-53.png)

---

Make the following settings
- Font is `Barlow`
- font weight is `600`
- Font size is `12`
- Check `Center the text vertically`

![bg right w:400](images/2022-11-26-00-42-07.png)

---

Then define the specified individual styles as the common style

- Open the `Style` pull-down in the `Image` setting
- Click `Create a new style..` at the bottom

![bg right w:400](images/2021-11-20-02-23-00.png)

---

- Enter `Label` in Style name
- Element style remains `Text`, indicating that it is the style of the text element
- Use style of remains `Text Image` and creates a style based on `Text Image`

![bg right w:400](images/2021-11-20-01-49-05.png)

---

Label should now be specified in the style.

![](images/2021-11-20-02-24-36.png)


Rather than defining the individual specified styles as a common style,
There is also a way to define the style first, but you can define the style individually
It is better to set the specified one as the common style
It is easy to work because you can create while checking the image in the design view.

---

Now let's apply the defined style to other labels.

- pet_detail: Name, Birthday, Gender
- pet_register: Image, Name, Birthday, Gender
- pet_weight_register: Weight

It's a little long and time consuming.

If you had separate styles from the beginning, you only had to change the style in one place, so if you come across screen elements with different meanings, you should be conscious of defining styles.

----

## Let's preview

![w:800](images/2022-11-26-00-47-20.png)

That's it for Style.

---

## Create logic

---

## Create logic

Logic is embedded in various places in the application.

- Give feedback on screen operations
- Extract and process data
- Switch screens by authority, etc.

Bubble can also embed logic in various places, so let's do it together.

---

## Return feedback for screen operation

---

## Return feedback for screen operation

Bubble can embed logic for screen elements.
It can be used to create and mix feedback for screen operations.

When you hover over the pet list, let's add a movement so that a red frame is attached.

![w:800](images/2022-11-26-00-53-48.png)

---

We will embed the logic in the image Element
- open pet_list
- Double-click the image Element of the pet image to open the settings
- Specify `Conditional` from the tab
- Click the `Define another condition` button

As I mentioned in specifying rules for whether or not to display responsive, here you can define how to change the property when the conditions and conditions are met.

![bg right w:600](images/2021-11-20-02-53-06.png)

---

First, let's see what conditions can be specified.

- The corresponding image Element, its parent element and other elements in the screen
- Login user
- New data search
- Current status such as current date, current position, page width, scroll position, etc.

In this way, you can see that various conditions can be specified.

![bg right w:400](images/2021-11-20-02-55-53.png)

---

This time, let's simply select the corresponding image `This Image`.

Then, the image states are listed next. There are many options here, but this time, select `is hovered`.

Now the condition is that the image in question is hovered over.

![w:400](images/2021-11-20-03-05-21.png)

---

Next, specify which properties to change when the conditions are met.
Click on `Select a property to change when true` and take a look inside.

- image source, alt attribute
- clickable, borders, etc.

I know that things can change.
What is listed here depends on the type of Element.

![bg right w:400](images/2021-11-20-03-09-36.png)

---

This time, when it is hovered, it will have a red border.
- Click `Border style - all borders`
- Change `None` to `Solid`
- It means that the border is changed from `none` to `show solid line`.

![bg right w:400](images/2021-11-20-03-16-54.png)

---

- Select `Select a property to change when true`
- Click `Border coloer - all borders`
- You will be able to specify the color, so select the defined Primary
- Similarly, next, specify `Border width - all boarders` and set `2`

![bg right w:400](images/2022-11-26-00-53-18.png)

This completes the settings.

---

## Let's preview

When I hover, a red frame appears.

![w:700](images/2022-11-26-00-53-48.png)

In this way, you can create products by embedding logic such as returning easy-to-understand feedback for user operations and switching screen decorations depending on the state.

---

## Extract and process data

---

## Extract and process data

You can extract only specific data or process or calculate the acquired data.
Make sure to display your pet's initials, age, and most recent weight.

![bg right w:600](images/2022-11-26-01-27-11.png)

---

## Advance preparation

Since we will be adding elements from now on, let's shorten the width of Name, Birthday, and Gender.
- In pet_detail, double click Name to open settings
- Hold down Shift and select from the Name label to the Gender text element
- Click the part where `Width` is displayed on the screen
- Specify `110` for W (width)
- Press the `Apply changes to elements` button

![bg right w:400](images/2022-11-26-01-01-14.png)

---

## display initials first

- Change the content of the Name label to `Name (Initial)` to indicate that it contains initials
![](images/2021-11-20-03-41-21.png)

---

- Select the text that gives the content of Name
- Click on the empty part of the text input field to give it focus
- type `(`
- Select `Insert dynamic data`
- Select `Current Page Pets` > `'s Name`
- `More...` should appear faintly, so click it

Various processing methods can be selected here. Let's take a look.

![bg right w:400](images/2021-11-20-03-47-44.png)

---

- Select `truncated to`
  - This means cut up to the specified number of characters
- Type `1` and confirm with Enter key
- Click on ``More'' again
- Select `:uppercase`
  - this means convert to upper case
  - (It doesn't make sense for those who have Japanese names)
- Click on the empty part of the text input field and enter `)`

![](images/2021-11-20-03-52-12.png)

---

## Let's preview

![w:700](images/2022-11-26-01-04-56.png)

---

## Display latest weight

- Copy and paste Birthday labels and text to place them
- Change the label to `Latest Weight`

![bg right w:600](images/2022-11-26-01-06-30.png)

---

- Open the setting of the text to reveal the Latest Wight and empty the text input area
- Focus and click `insert dynamic data`
- Click on `Do a search for`
  - You mean to search data

![bg right w:600](images/2021-11-20-04-00-08.png)

---

Specifies to get the weight of the pet currently displayed on the page

- Specify `PetWeightLogs` for `Type`
- Click the `Add a new constraint` button
- Click the condition input field that appears, and specify `Pet`, `=`, and `Current Page Pets` in that order

You can get it under various conditions, so let's take a look at what conditions there are

![bg right w:600](images/2022-11-26-01-08-01.png)

---

Specifies to sort in descending order of creation date, that is, in order of newest creation.

- Specify `Created Date` for `Sort by`
- Specify `yes` for `Descending`
- Close

It is easy to forget to specify the sort order, but it is often important.

![bg right w:400](images/2021-11-20-04-06-52.png)

---

Display the latest 1 weight
- Click `More` in the text entry field to see what's inside
- Since we want to get the first item, specify `:first item`
- Next, specify `'s WeightKg`
- Click on the blank space and enter `kg`

This completes setting the latest weight.
Let's remember it as a method of data extraction and list processing.

![bg right w:600](images/2021-11-20-04-10-59.png)

---

## Let's preview.

![w:600](images/2022-11-26-01-09-47.png)

---
#### <Advanced>

## A little sidetrack,
## Let's take a look at Number More and Date More.

Bubble provides various processing and calculation methods for numbers and dates as well.

---

#### <Advanced>

## calculate age

Next, give your age. As you saw earlier, you can process and calculate numbers and dates, but age calculation seems a little difficult, so I'm thinking of embedding the code directly.

By introducing a plugin in Bubble, you can operate simple processing using a programming language called javascript.

---

#### <Advanced>

To embed javascript code, use a plugin called `Toolbox`.
Let's install it.

- Specify `Plugins` in the left menu
- Enter `tool` in the search text box (searching will take some time)
- Press the `Install` button of `Toolbox` that appears at the top of the search results

![bg right w:600](images/2021-11-20-04-25-21.png)

---

#### <Advanced>

There are two ways to embed code in Toolbox.

- Execute with `Run javascript` on Workflow / Receive with `Javascript to Bubble` on Design
  - Used for complex processing that spans multiple lines
- Execute and receive with `Expression` on Design
  - Used for processing that ends in a single shot

---

#### <Advanced>

Now let's calculate your age.
Do it with `Run javascript` / `Javascript to Bubble`. First, put `Javascript to Bubble` on the pet_detail screen.

- Select `javascript to Bubble` from `Visual elements` on the left menu
- Put it in an unobtrusive place such as the bottom of the screen
- Since it is for receiving the result of javascript, it is not displayed at the time of execution such as preview

![bg right w:400](images/2021-11-20-04-45-28.png)

---

#### <Advanced>

- Specify `age` for `bubble_fn_suffix`
- Check `Publish value`
- Specify `number` for `Value type`

Now, if you pass a value from javascript to the `bubble_fn_age` function (block of processing), you will be able to receive it with this screen element.

![bg right w:300](images/2021-11-20-05-17-45.png)

---

#### <Advanced>

Next, define where to execute javascript.
- Select Workflow from the left menu
- There are squares, select the rightmost `Click here to an event...`
- Select `General` > `Page is loaded`

![bg right w:700](images/2021-11-20-04-52-26.png)

---

#### <Advanced>

- Click `Click here to add an action...`
- Click `Plugins` > `Run javascript`
- Since the setting opens, paste the code of the next page in the `Script` field

![bg right w:300](images/2021-11-20-05-00-40.png)

---

#### <Advanced>

```
//Date of birth
const birthday = {
    year: ,
    month: ,
    date:
  };

function getAge(birthday){

    //today
    let today = new Date();
 
    // this year's birthday
    let thisYearsBirthday = new Date(today.getFullYear(),birthday.month-1, birthday.date);
 
    //age
    let age = today.getFullYear() - birthday.year;

    if(today < thisYearsBirthday){
        // My birthday hasn't come yet this year
        age--;
    }

    return age;
}

bubble_fn_age(getAge(birthday));
```

---

#### <Advanced>

Insert the date with `insert dynamic data` after `year:`,`month:`,`date:` on the 3rd to 5th lines
- Place the cursor after `year:` (before `,`)
  - `insert dynamic data`>`Current Page Pets`>`'s Birthday`
  - `More`>`formatted as 11/20/21`
  - Specify `Custom` for `Format type`
  - Specify `yyyy` for `Custom format`
- Similarly, after `month:`, insert `Custom format` as `m`
- Similarly, after `date:`, insert `Custom format` as `d`

*The image after input is on the next page

---

#### <Advanced>

Image after input
![w:800](images/2021-11-20-05-20-55.png)

---

#### <Advanced>

Let's arrange the screen elements to display
- Copy and paste Birthday labels and text
- Change label to Age
- Specify the contents of the text as `JavascripttoBubble A`>`'s value`

---

#### <Advanced>

## Let's preview

![w:600](images/2022-11-26-01-20-14.png)

---

#### <Advanced>

Next, I would like to display how old dogs and cats are when converted to the age of cats and dogs.
Use `Expression`.

- Select `Expression` from Visual elements and place it next to `Javascript to Bubble`
- Enter `24 + (` in Expression
- Insert `JavascripttoBubble A`>`'s value` with `insert dynamic data`
- Then enter ` -2) * 4`
- Specify `number` for Result type

![bg right w:500](images/2021-11-20-05-30-14.png)

---

#### <Advanced>

Make display settings.
- Change the Age label to `Age (as Dog/Cat)` so that it is easy to understand that it includes the age of dogs and cats
- Enter `(` after what was originally entered in the Age text content
- Insert `Expression A`>`'s value` with `insert dynamic data`
- type `)`

![bg right w:500](images/2021-11-20-05-34-15.png)

---

#### <Advanced>
## Let's preview
![w:500](images/2022-11-26-01-25-08.png)

---

## Switch screens by authority

---

## Switch screens by authority

Up to this point, we have explained how to incorporate logic in parts such as feedback to screen operations and data extraction and processing.

Next, I would like to add logic that spans multiple functions.

Do the following:
- Divide users into Pet Owners and Pet Advisors
- The owner can use the screens and functions that have been created so far
- Advisors can use screens and functions dedicated to advisors

---

As a flow of development, it will be mixed in the following order.
- Add a field that can distinguish between owner and advisor to user information
- At the time of user registration, it is possible to select and register as an owner or an advisor
- Create advisor list screen and detail screen
- Switch the screen transition destination after login/sign-up depending on whether you are an owner or an advisor

It takes a lot of steps, but there are many products that handle multiple user types, so let's learn it.

---

## Add a field that can identify a user

First of all, we will make it possible to retain the difference in the role of the owner or the adviser in the data.

It can be stored in text like the male and female of pets, but for values ​​that are specified from fixed options, it is easier to handle by defining options in advance and using them. Bubble provides a mechanism called Option set, so let's use it.

---

Let's set the Options

- Go to `Data` on the left menu > `Option sets` on the tab
- Enter `Role` in `New Option set` and press the Create button
- Role is created as a new Option set

![bg right w:600](images/2021-11-20-06-14-02.png)

---

We will add specific Options to the Option set called Role. This time, we will create a `Pet Owner` and a `Pet Advisor`.

- Enter `Pet Owner` in the `New Option` at the bottom right of the screen and press the Create button
- Similarly, enter `Pet Advisor` in `New Option` and press the Create button

Settings are complete

![bg right w:800](images/2021-11-20-06-17-29.png)

---

Next, let's add the role as an attribute of the user

- Go to `Data` on the left menu > `Data types` on the tab
- Select `User`
- Click the `Create a new field` button on the bottom right of the screen

![bg right w:600](images/2021-11-20-06-20-20.png)

---

- Enter `Role` in `Field name`
  - This can be named anything as long as it is descriptive
- Select `Role` for `Field type`
  - What is specified here is the `Role` as the `Option set` created earlier.
- Press the Create button

![bg right w:600](images/2021-11-20-06-23-26.png)

---

Since we've added a new field, Roles will be empty for users we've already created. It will cause inconsistency later, so let's apply a patch (data correction) to the existing data.

- Go to the `App Data` tab and select `All Users`
- Since the table is displayed, click the pen icon on the left end of the table and edit one by one
  - All users created now should be owners, so specify `Pet Owner` for `Role`
![](images/2021-11-20-06-27-18.png)

---

It is OK if all lines in Users have `Role` set to `Pet Owner`

![](images/2021-11-20-06-29-53.png)

---

## Allow specifying a role when registering a user

Now, let's make it possible to register by specifying whether it is an owner or an advisor when registering a user.

I've been using the registration screen prepared by Bubble, but I'll put my hand on it.

---

- Go to login page `index`
- Select `Dropdown` from `Input forms` in the `Design` menu and place it below the password input field
- The login screen is a mixture of signup and login and may not be well placed. `Let's add it while checking in the Elements tree.
- To select values ​​in a group, hold down Ctrl (Cmd for Mac) and double-click to select.

![bg right w:600](images/2022-11-26-01-42-39.png)

---

- Match the width of the Dropdown to make it look nice
- Dropdown settings are as follows
  - Element name: `Dropdown Role`
  - Placeholder: `Choose a role...`
  - `Choice style`: `Dynamic choices`
  - `Type of choices`: `Role`
  - `Choices source`: `All Roles`
  - `Option caption`: `Current option`>`'s Display`
  - `Default value`: `Pet Owner`
  - Check `This input should not be empty`:


*Screen image on the next page

---

Image after input
![w:600](images/2022-11-26-01-46-54.png)

---

Next, make sure that the entered Role is set at the time of user registration

- Go to `Workflow` from the left menu > `Button Sign up is clicked` from the lined squares > `Sign the user up` from the lined Actions
- Click the `Change another field` button in the Action settings screen
- Since the input field appears, select `Role` = `Dropdown Role` `'s value`

![bg right w:600](images/2021-11-20-06-45-29.png)

---

## Let's preview and check the operation

You have successfully registered an account as an advisor! (No dedicated screen yet)

![w:300](images/2022-11-26-01-52-18.png)
![w:500](images/![](images/2021-11-20-06-55-01.png).png)

---

## Create Advisor list screen

Let's create an advisor list screen

- bOpen the menu next to the logo and select `Add a new page...`
- Enter `pet_list_for_advisor` in `Page name`
- Select `pet_list` in `Clone from`
- A new screen is created

![bg right w:600](images/2021-11-20-06-59-31.png)

---

Advisors can see all registered pets.- Delete original search criteria
  - Click `Do search for` in Data source
  - Click the trash can icon to delete the part that specifies `Created By = Current User`
- Advisors need to view many pets, so keep the size of each cell small.
  - Specify 150px for `Min width` and 120px for `Min height`
![bg right w:600](images/2022-11-26-02-13-13.png)

---

When an advisor logs in, transition to the advisor list screen

- open `index` page
- Go to `Workflow` from the left menu > `Button Sign up is clicked` from the lined squares > `Sign the user up` from the lined Actions
- Click the `Change another field` button in the Action settings screen
- Since the input field appears, select `Role` = `Dropdown Role` `'s value`

![bg right w:600](images/2021-11-20-06-45-29.png)

---

### Let's preview

Nothing comes out! ? why? ?

![](images/2021-11-20-07-22-55.png)

Because you don't have the authority.

---

### Permission control in Bubble

I'm glad I didn't realize it until now, but Bubble strictly restricts access to Data.

Go to `Data` on the left menu > `Privacy` on the tab.
By default, data is only accessible to the creator.

Naturally speaking, it is natural.

![bg right w:600](images/2021-11-20-07-26-09.png)

---

Now, if you're an advisor, we'll add permissions that allow you to see all the data.

- In the `Privacy` tab, select `Pets`
- Click the `Define a new rule` button
- Enter `Visible to advisor` in the Rule name
- Select `Current User` `'s Role` `is` `Pet Advisor` for When
  - The condition is that the user was an advisor

Now if you're an Advisor, you'll be able to see stats for all your pets.
It is also possible to limit the fields that can be referenced for each rule, but we will not use it this time.

*Screen image on the next page

---

![](images/2021-11-20-07-32-23.png)

Now add a rule to `PetWeightLogs` in the same way.
Advisors should now be able to see all the data.

---

## Let's preview
yay
![](images/2022-11-26-02-14-09.png)

---

Next, control the transition destination at login.

For advisors, add an Action to transition to pet_list_for_advisor when transitioning to pet_list

---

- Open Workflow on index page
- Click `Click here to add an event..`
- Select `General` > `Page is loaded`
- Click `Click here to add an action..`
- Click `Navigation` > `Go to page..`
- Open Settings, select `pet_list_for_advisor` for Destination
- Select `Current User` `sRole` `is` `Pet Advisor` for `Only when`

![bg right w:700](images/2022-11-26-02-24-57.png)

---

## Let's preview & check the operation

Login as Advisor
![w:900](images/2022-11-26-02-27-58.png)

---

After logging in as owner
![w:900](images/2022-11-26-02-28-44.png)

good good

---

#### <Advanced>

## An account was created without permission with an advisor,
## Is it okay to see information without permission?

---

#### <Advanced>

## Let's make it so that you can't start using it unless the system administrator approves it

---

#### <Advanced>

## will do the following

- Add a field to user information indicating whether they are approved as advisors
- Access to data must be approved as well as being an advisor
- Advisor pet list shows message under review if unapproved

---
#### <Advanced>

## Add a field to user information whether they are approved as advisors

- From the left menu, click `Data` > `Data types` > `User`
- Click the `Create a new field` button on the bottom right of the screen
- Enter `Approved As Advisor` in Field name
- Select `yes/no` for Field type
- Click the Create button

![bg right w:600](images/2021-11-20-08-15-18.png)

---

#### <Advanced>

Since there is a column called `default` in the added field, set `no` (or `no`).
At the time it is created, it will be in an unapproved state.
 
 ![](images/2021-11-20-08-18-00.png)

---

#### <Advanced>

For existing users, leave all `Approved As Advisor` to `no`
(Troublesome and depressed... but important!)

![](images/2021-11-20-08-21-51.png)

---

#### <Advanced>

## also see if permission to access data is authorized

- From the left menu, click `Data` > tab `Privacy` > `Pets`
- Click `Pet Advisor` at the end of the part that describes When condition of `Visible to advisor`
- ``More'' will appear, so click ``More''
- Select `and` `Current User` `'s Approved As Advisor` `is "yes"`
- Do the same for `PetWeightLogs`

---

#### <Advanced>

Let's check the operation
Try logging in as a user whose `Approved As Advisor` is `no`

![](images/2022-11-26-02-36-18.png)

good

---

#### <Advanced>

What if `Approved As Advisor` is `yes`?

![](images/2022-11-26-02-35-51.png)

good

---

#### <Advanced>

## If unapproved, output a message that it is under review

- Open the `Design` menu on the pet_list_for_advisor screen
- Add `Popup`
- Add a text Element above the `Popup` with a message that it is under review
![bg right w:700](images/2021-11-20-08-33-33.png)

---

#### <Advanced>

- Go to Workflow from menu
- Click `Click here to add an event..`>`Page is loaded`
- Click here to add an action..`>`Element Actions`>`Show`
- Specify `Popup A` for Element
- Specify `Current User` ``s Approved As Advisor` `is "no"` for Only when

![bg right w:600](images/2021-11-20-08-38-07.png)

---

#### <Advanced>

## Let's check the operation

yes adviser
![](images/2022-11-26-02-35-51.png)

good

---

#### <Advanced>

if no
![](images/2022-11-26-02-39-20.png)

good

---

#### <Advanced>

## How do sysadmins find out?

---

#### <Advanced>

## Let's notify the system administrator by e-mail when the advisor is registered

---

#### <Advanced>

## Let system administrators be notified by email

- open `index` page
- Go to Workflow from the menu and select `Button Sign up is clicked`
- Click `Click here to ad an action...`> `Email`>`Send Email`
- Drag the position of Action before `Go to page pet_list` to move it

![bg right w:600](images/2022-11-26-02-41-30.png)

---

#### <Advanced>

- Set your own email address in To
- Sender name is `PetLog`
- Subject is `New Advisor Registered`
- For Body, select `Input Email(sign up)` `'s value` with `dynamic data isert` at the end of the body below
```
New Advisor has been Registered.
Please check it.

Email:
```

![bg right w:400](images/2022-11-26-02-43-23.png)

---

#### <Advanced>

- Select `Dropdown Role` `s value` `is` `Pet Advisor` for Only When

![bg right w:500](images/2021-11-20-11-26-00.png)

---

#### <Advanced>

## Let's check the operation
After signing up as an advisor
![w:600](images/2021-11-20-08-50-37.png)
came

---

#### <Advanced>

if the owner

Yeah, no. Yay


---

#### <Advanced>

## Exercises

An opportunity for the advisor to approach the owner, or the owner to approach the advisorLet's create a Noh performance

- Example: You can send advice to the owner
- Example: You can advertise
- Example: You can ask your advisor for advice, etc.

---

### Today's Review

---

### I made a design

- Created a screen that fits the display size
  - Using a technique called responsive web design, we used the following rules to control the appearance according to the display size.
    - Placement rules within parent elements
    - element sizing rules
    - Display presence/absence rule
- I tried using Style
  - Edit and add styles, and apply styles individually

---

## I made logic

- Feedback on screen operation was returned
- Extracted and processed data
- Switched screens by authority

Together we saw how you can embed logic in various places with Bubble

---

## At the end

This concludes the Basic Lecture on Bubble.
After this, it will be an application version of Bubble.

There are many features that I haven't touched on yet.
Bubble has plenty of manuals and references, so
If you adopt Bubble, please take advantage of it.

Here is the manual.
https://manual.bubble.io/

References appear when you hover over something on the screen that you don't understand.
For most features, links to references pop up.

---

## Thank you for your hard work