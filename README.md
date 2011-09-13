0 Regexes
---------
0 Try-catch blocks
------------------
No browser sniffing
-------------------
Only 3kb (minified and gzipped)
-------------------------------

Jaguar is a new standalone CSS selector engine developed for the [Shrike](https://github.com/alpha123/Shrike) JavaScript library, which basically supersedes [Puma](https://github.com/alpha123/Puma).

Jaguar was designed from the ground up for speed and extensibility, though I'll freely admit it's not as extensible as Puma. A fast method for matching elements with against a CSS selector -- commonly used for event delegation -- is built-in and often beats the browser's native `matchesSelector` implementation.

Jaguar supports most of the CSS3 selectors, including the more esoteric selectors such as `:root > div[rel|=junkfood] ~ p:nth-last-of-type(5n-7)` (if anyone actually uses that, I'd love to know).

It's syntax is just like Sizzle/Slick/Puma/<insert your favorite CSS selector engine here>:

    Jaguar.search(String selector[, DOMElement|DOMDocument context])
    // Or simply:
    Jaguar(String selector[, DOMElement|DOMDocument context])

The `Jaguar.search()` function always returns a true Array.

Calling `Jaguar()` as a function does exactly the same thing as `Jaguar.search()`.

Jaguar also has a `match()` method, mentioned above, which returns a boolean:

    Jaguar.match(Jaguar('#id')[0], '#id') // true
    Jaguar.match(Jaguar('#cake')[0], '.edible') // hopefully true

Full docs will be available in the docs/ folder and at https://alpha123.github.com/Jaguar/docs/.