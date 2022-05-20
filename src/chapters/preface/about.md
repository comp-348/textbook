---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.10.3
kernelspec:
  display_name: OCaml
  language: OCaml
  name: ocaml-jupyter
---

# About This Book

**Reporting Errors.** If you find an error, please report it! Or if you have a
suggestion about how to rewrite some part of the book, let me know. Just go to
the page of the book for which you'd like to make a suggestion, click on the
Github icon (it looks like a cat) near the top right of the page, and click
"open issue" or "suggest edit". The latter is a little heavier weight, because
it requires you to fork the textbook repository with Github. But for minor edits
that will be appreciated and lead to much quicker uptake of suggestions.

**Background.** This book is offered independently for use at Concordia Univerisyt
for a second-year programming course. Most students have had two semesters of
introductory object-oriented programming in Java. Frequent comparisons are therefore
made to it. Readers who have studied similar languages should have no difficulty
following along. The book does not assume any prior knowledge of the programming
paradigms discussed, but it does assume that readers have prior experience
programming in some mainstream imperative language.

**Collaborative Annotations.** At the right margin of each page, you will find
an annotation feature provided by [hypothes.is][hypothesis]. You can use this to
highlight and make private notes as you study the text. You can form study
groups to share your annotations, or share them publicly. Check out these
[tips for how to annotate effectively][tips].

[hypothesis]: https://web.hypothes.is/
[tips]: https://web.hypothes.is/annotation-tips-for-students/

**Executable Code.** Many pages of this book have code embedded in them.
The output of that code is already shown in the book. Here's an example:

```{code-cell} c
#include <stdio>
int main() {
  printf("Hello World!");
}
```

You can also edit and re-run the code yourself to experiment and check your
understanding. Look for the icon near the top right of the page that looks
like a rocket ship. In the drop-down menu you'll find two ways to interact
with the code:

- _Binder_ will launch the site [mybinder.org](https://mybinder.org), which is a
  free cloud-based service for "reproducible, interactive, shareable environments
  for science at scale." All the computation happens in their cloud servers, but
  the UI is provided through your browser. It will take a little while for the
  textbook page to open in Binder. Once it does, you can edit and run the code
  in a [_Jupyter notebook_][jupyter]. Jupyter notebooks are documents (usually
  ending in the `.ipynb` extension) that can be viewed in web browsers and used
  to write narrative content as well as code. They became popular in data
  science communities (especially Python, R, and Julia) as a way of sharing
  analyses. Now many languages can run in Jupyter notebooks, including OCaml.
  Code and text are written in _cells_ in a Jupyter notebook. Look at the "Cell"
  menu in it for commands to run cells. Note that Shift-Enter is usually a
  hotkey for running the cell that has focus.

- _Live code_ will actually do about the same thing, except that instead of
  leaving the current textbook page and taking you off to Binder, it will modify
  the code cells on the page to be editable. It takes some time for the
  connection to be made behind the scenes, during which you will see "Waiting
  for kernel". After the connection has been made, you can edit all the code
  cells on the page and re-run them.

Try interacting with the cell above now to make it print a string of your choice.

```{tip}
When you write "real" code, this is not the interface you'll be using.
You'll write code in an editor such as Visual Studio Code or Atom, and you'll
compile it from a terminal. Binder and Live Code are just for interacting
seamlessly with the textbook.
```

**Downloadable Pages.** Each page of this book is downloadable in a variety of
formats. The download icon is at the top right of each page. You'll always find
the original source code of the page, which is usually [Markdown][md]&mdash;or
more precisely [MyST Markdown][myst], which is an extension of Markdown for
technical writing. Each page is also individually available as PDF, which simply
prints from your browser. For the entire book as a PDF, see the paragraph about
that below.

**Exercises and Solutions.** At the end of each chapter except the first, you
will find a section of exercises. The exercises are annotated with a difficulty
rating:

- One star [&starf;]: easy exercises that should take only a minute or two.

- Two stars [&starf;&starf;]: straightforward exercises that should take a few
  minutes.

- Three stars [&starf;&starf;&starf;]: exercises that might require anywhere
  from five to twenty minutes or so.

- Four [&starf;&starf;&starf;&starf;] or more stars: challenging or
  time-consuming exercises provided for students who want to dig deeper into the
  material.

It's possible we've misjudged the difficulty of a problem from time to time. Let
us know if you think an annotation is off.

Please do not post your solutions to the exercises anywhere, especially not in
public repositories where they could be found by search engines. {{ solutions }}

**PDF.** A <a href="../../programming_paradigms.pdf">full PDF version of this
book</a> is available. It does not contain the embedded videos, annotations, or
other features that the HTML version has. It might also have typesetting errors.
At this time, no tablet (ePub, etc.) version is available, but most tablets will
let you import PDFs.
