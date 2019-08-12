# HTML-CSS-Styleguide

*“Everything in your life should be easy as possible.. as well as your code should”*

**HTML:**

*1. Indents and formatting standards:*
- We always use two spaces for each new stroke of the code.
- Each nested element should be shifted with two spaces from the parent element.
- Remove trailing white spaces after the elements. It can complicate GIT diffs.
- Try to avoid code lines longer than 80 characters
- Break long lines of code. In case if you have a lot of attributes on the tag it’s better to put each other on the next line.
example:
```
<ion-searchbar 
  *ngIf="!isInfoView" 
  (ionInput)="getItems($event)" 
  (ionFocus)="onFocus()"> 
  class="input-searcher" 
  [class.hidden-news]="isMoreNews" 
</ion-searchbar>
```
- You must avoid of using the spaces in the names of files. However, you must use quotes if the value contains spaces and you decided to use these.
- Separate words in ID and class names by a hyphen. (.unordered-list {})
- All code has to be lowercase: This applies to HTML element names, attributes, attribute values, CSS selectors.
- Do not use unnecessary blank lines and indentation between elements.

*2) Code validation:*
- Code must be valid according to the W3C specifications and standards code. Unless that is not possible due to otherwise unattainable.
HTML files must be checked here: https://validator.w3.org/
- Always close the tags not to waste your time with the incorrect rendering of the page structure. Unless these tags are self-closing.

*3) Encoding and MetaData:*
- Encoding Use UTF-8 (no BOM).

*4) Semantic:*
- We must always use semantic elements that were added in the HTML5. This allows us to define the sense and make easy-to-read structure of our markup document.
- Nevertheless, don’t use semantic tags to wrap self-explanatory elements in additional tag. I.e. don’t wrap the headings (h1, h2, etc.) into additional <header> tag.

*5) Class naming:*
- Use ID and class names that are as short as possible but as long as necessary.
- You should always name selectors according to its’ content. Use meaningful or generic ID and class names.
- Instead of presentational or cryptic names, always use ID and class names that reflect the purpose of the element.

*6) Code comments:*
- Create self-explanatory, clear and easy-to-read code which help other team members understand everything without any comments.

**CSS:**

*1) General standards:*
- Avoid using HTML tags in CSS selectors. #header is overly specific compared to, for example .header and is much harder to override
```
/* Not recommended */
ul.undordered-list {}
/* Recommended */
.undordered-list {}
```
- Always prefer using a class over HTML tags.
- Don't use ids in selectors
- Try to avoid huge nestings. It’s possible to style each element from the parent element. Don’t nest more than 3 levels deep
- Indent all block content with two spaces.
- Separate selectors and declarations by new lines. (Always start a new line for each selector and declaration.)
- Don't  use !important. It greatly increases the power of a CSS declaration, making it extremely tough to override in the future. It’s - only possible to override with another !important declaration later in the cascade.
- Don’t use margin-top. Vertical margins collapses. Always prefer padding-top or margin-bottom on preceding elements
- Use shorthand properties where possible.
- Omit unit specification after “0” values, unless required. (Do not use units after 0 values unless they are required.)

*2) Validation:*
- HTML files must be checked here: https://jigsaw.w3.org/css-validator/

*3) Declaration Order: (Optional)*
- Related property declarations should be grouped together following the order 
* Positioning
* Box model
* Typographic
* Visual
* Misc
- Positioning comes first because it can remove an element from the normal flow of the document and override box model related styles. - - The box model comes next as it dictates a component's dimensions and placement.
- Everything else takes place inside the component or without impacting the previous two sections, and thus they come last.
```
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;
  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;
  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;
  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;
  /* Misc */
  opacity: 1;
}
```
