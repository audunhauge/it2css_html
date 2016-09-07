A note about this fork
==============

This fork is essentially the same as https://github.com/GitbookIO/plugin-exercises with the changes of [PR 11](https://github.com/GitbookIO/plugin-exercises/pull/11) included to fix [issue 6](https://github.com/GitbookIO/plugin-exercises/issues/6).

This repo isn't actively maintained and will hopefully become obsolete once an official fix exists for [issue 6](https://github.com/GitbookIO/plugin-exercises/issues/6).

To use this temporary plugin in your gitbook, specify:

```
{
    "plugins": ["exercises-tmp-fixed-6"]
}
```

Below is the original `README.md`.


Interactive exercises in a gitbook
==============

With this plugin, a book can contain interactive exercises (currently only in Javascript). An exercise is a code challenge provided to the reader, who is given a code editor to write a solution which is checked against the book author's validation code.


## How to use it?

To use the exercises plugin in your Gitbook project, add the `exercises` plugin to the `book.json` file, then install plugins using `gitbook install`.

```
{
    "plugins": ["exercises"]
}
```

## Exercises format

An exercise is defined by 4 simple parts:

* Exercise **Message**/Goals (in markdown/text)
* **Initial** code to show to the user, providing a starting point
* **Solution** code, being a correct solution to the exercise
* **Validation** code that tests the correctness of the user's input

```
{% exercise %}
Define a variable `x` equal to 10.
{% initial %}
var x =
{% solution %}
var x = 10;
{% validation %}
assert(x == 10);
{% context %}
// This is context code available everywhere
// The user will be able to call magicFunc in his code
function magicFunc() {
    return 3;
}
{% endexercise %}
```

The old format (`gitbook < 2.0.0`) is still supported but deprecated.
