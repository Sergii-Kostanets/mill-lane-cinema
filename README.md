# Exercise 3 fixes: Mill Lane Cinema

Name:

## Mistake 1

**Page or file:** `index.html`  
**What I saw in DevTools:** The stylesheet request returned 404, and the page had no styles.  
**What was wrong:** The link points to `css/styles.css`, but `styles.css` is in the same folder as `index.html`.  
**How I fixed it:** Change the link to `href="styles.css"`.

## Mistake 2

**Page or file:** `about.html`  
**What I saw in DevTools:** The stylesheet request returned 404, and the page had no styles.  
**What was wrong:** The link points to `style.css`, but the stylesheet is named `styles.css` and is in the same folder.  
**How I fixed it:** Change the link to `href="styles.css"`.

## Mistake 3

**Page or file:** `styles.css`, `h1, h2` rule  
**What I saw in DevTools:** The `colour` declaration was ignored; the heading color was not set by this rule.  
**What was wrong:** `colour` is not a CSS property name.  
**How I fixed it:** Change `colour` to `color`.

## Mistake 4

**Page or file:** `styles.css`, `header, footer` rule  
**What I saw in DevTools:** The `text-align` declaration was ignored.  
**What was wrong:** `centre` is not a valid CSS value for `text-align`.  
**How I fixed it:** Change `centre` to `center`.

## Mistake 5

**Page or file:** `styles.css`, `highlight` rule  
**What I saw in DevTools:** The rule did not match the “Paper Boats” list item, which has the class `highlight`.  
**What was wrong:** `highlight` selects an HTML element named `<highlight>`, not elements with the `highlight` class.  
**How I fixed it:** Add the class selector dot: change `highlight` to `.highlight`.

## Mistake 6

**Page or file:** `styles.css`, `footer` rule  
**What I saw in DevTools:** The footer's `color` declaration was flagged as part of an invalid declaration; the footer text color was not applied as intended.  
**What was wrong:** There is no semicolon after the `background-color` value, so the following `color` property is not separated from it.  
**How I fixed it:** Add a semicolon after `#2b2b3a`.

## Mistake 7

**Page or file:** `styles.css`, `main ul .member` rule  
**What I saw in DevTools:** The member list item's computed color was `dimgray`; this more-specific selector overrode the `darkred` color from `.member`.  
**What was wrong:** The selector applies the general list color specifically to the `.member` item, preventing the member-specific color from taking effect.  
**How I fixed it:** Change the selector to `main ul li`, so the general list color applies to list items and `.member` can set the member item's color to `darkred`.

## Validator results

- **HTML validator:** No errors.
- **CSS validator:** Reported `colour`, the invalid `centre` value, and the missing semicolon before `color` in the footer rule.
- **Only DevTools showed:** The two stylesheet requests failing because of incorrect paths, the `highlight` selector not matching the class, and the member color being overridden by the more-specific selector.
