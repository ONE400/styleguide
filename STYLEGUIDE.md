# ONE400 Style Guide
Outlined below are a few guidelines to follow to keep the HTML/CSS needs to be healthy and flexible and semantic.

## Goals
- Sensible, well-factored SCSS
  - Alternatively we can use CSS Custom Properties if the project doesnt use the other SCSS features listed below
    - (https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- Use flexbox for layout
- Avoid use of Bootstrap if possible
- Semantic class names based on type/function such as `login-box` instead of `col-sm-3 bold pad-right`
- Avoid using IDs as much as possible
- Avoid page-specific styles
- Be concious of the difference between presentation and content
  - Content tags: p, h1, em, etc
  - Layout tags: div, label, section, etc

## Layout
- Use flexbox for layout
- Use SCSS `@extend` to build/group similar elements
- Use `vw/vh/%` to size layout instead of `px`, if possible
- Use `px` for text/images
- Use HTML5 semantic tags where appropriate:  `<nav> <header> <main> <footer> <section> <aside> <article>`, etc instead of `<div id='navigation'>` or `<div class='content-block'>` for example
- Only use h* tags (h1,h2, etc) for content, use the label tag for labeling sections

## Whitespace
- Use tabs instead of spaces
- Do not commit whitespace

## Forms
- Wrap related form elements in `<fieldset>` tags for accessability
- Don't use `<input type="number" />` for non-incrementing numeric input. Instead use `<input type="text" inputmode="numeric" pattern="[0-9]*">`. [Reference](https://technology.blog.gov.uk/2020/02/24/why-the-gov-uk-design-system-team-changed-the-input-type-for-numbers/)

## Presentation
- Avoid hard-coding colors all over, try to keep colors in the `_palette.scss`. Follow examples in `_mixin.scss`, etc.

## Javascript
- Javascript hooks should use the data attribute in order to increase clarity. For example: `<ul data-js-hook="toggle-plan">..</ul>` and accessed via `$("ul[data-js-hook='toggle-plan'])`. No CSS should use these classes. NOTE: there is danger here in increased coupling between behavior and structure. Use deliberately and sparingly.

## Media Queries
SCSS lets you put media queries inside tags, so keep areas of the code topical. For example:

    body{
        font-size: 18px;
        @media(max-device-width: 480px) { font-size: 32px; }
    }

## Images
- Create WebP versions of images for browsers that can use it
  - WebP Lossless for PNGs
  - WebP Lossy for JPGs
  - Keep fallback versions of the images for browsers that cant
  - See the following for more information: https://css-tricks.com/using-webp-images/

## Accessibility
- Use HTML5 semantic tags where appropriate:  `<nav> <header> <main> <footer> <section> <aside> <article>`, etc instead of `<div id='navigation'>` or `<div class='content-block'>` for example
- Use ARIA attributes where appropriate: https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA
- Web Accessability Standards: https://accessible.org/was/

## Audits
- Open Chrome Inspector/DevTools panel and go to the Audits tab and run the Audit for both desktop and mobile
    - Goal is 90+ on each
- Confirm scores on https://developers.google.com/speed/pagespeed/insights/

## Git Workflow

Article on git terminal basics: https://www.liquidlight.co.uk/blog/git-for-beginners-an-overview-and-basic-workflow/

- Create a private (feature) branch off a public branch (such as staging or master)
- Regularly commit your work to this private branch
- Merge the private branch back into the public branch
  - Use `git merge -no-ff <private branch>` when working solo
  - Use a GitHub Pull Request when working with a Project Manager

For a more indepth workflow: https://sandofsky.com/workflow/git-workflow/
Article on git branch naming conventions: https://deepsource.io/blog/git-branch-naming-conventions/
Article on git best practices: https://sethrobertson.github.io/GitBestPractices/


## Resources
- https://philipwalton.com/articles/decoupling-html-css-and-javascript/
- https://www.ostraining.com/blog/coding/bootstrap-right-way/
- https://www.sitepoint.com/sass-semantically-extend-bootstrap/
- https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout
- https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- https://css-tricks.com/using-webp-images/
- https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties
- https://www.liquidlight.co.uk/blog/git-for-beginners-an-overview-and-basic-workflow/
- https://sandofsky.com/workflow/git-workflow/
