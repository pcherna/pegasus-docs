CSS
===

## Supported Frameworks

Pegasus sites can be built using [Bootstrap 5](https://getbootstrap.com/) or [Bulma](https://bulma.io/).
The look and feel of the site is slightly different between the two, but the overall layout and
color scheme is the same.

TODO: Add screenshots.

If you're not sure which framework you want to use, you can also build Pegasus for both frameworks,
and change dynamically at runtime.

## CSS File Structure

CSS source files live in the `assets/styles` folder, and are compiled into the `static/css` folder.
Styles are written using [Sass](https://sass-lang.com/), which provides many benefits
and features on top of traditional CSS.

**Modifying CSS requires having a functional [front-end build setup](/front-end/).**

All versions of Pegasus contain two main sets of styles:

- Styles that are *framework-independent* are contained and imported in `assets/styles/app/base.sass` 
  and compiled into `static/css/site-base.css`.
- Styles that *extend or override the CSS framework* are contained in `assets/styles/app/<framework>/`
  and compiled into `static/css/site-<framework>.css`.

If you are using a single framework, this split is not required and you can optionally combine everything
into a single file by importing the styles from `base.sass` into your framework file and deleting `site-base.css`.
This optimization is completely optional.

### Pegasus CSS

In addition to the above structure, Pegasus also ships with its own set of CSS classes to provide compatibility
across frameworks. These are mainly used in the examples and in JavaScript files.

Pegasus CSS classes are defined in `pegasus/<framework>.sass`, and they all begin with `pg-`.
You are welcome to leave them in and use them throughout your project.

If you prefer, you can also replace them with the native framework classes (for example, replacing all instances
of `pg-column` with `column` on Bulma, or `col-md` on Bootstrap).