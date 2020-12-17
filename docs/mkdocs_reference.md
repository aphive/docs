--8<-- "includes/abbreviations.md"

# What can I do in pages?

!!! note
    Images used below are provided by [Placeholder.com](Placeholder.com), a free image placeholder service for web designers.

## Abbreviations
Add the abbreviations and meaning in the `includes/abbreviations.md` file like this:

```yaml
*[HTML]: Hypertext Markup Language
*[W3C]: World Wide Web Consortium
```

_Example_:

=== "docs/page.md"

    ```` markdown
    The HTML specification is maintained by the W3C.

    --8<--​ "includes/abbreviations.md"
    ````

=== "includes/abbreviations.md"

    ```` markdown
    *[HTML]: Hyper Text Markup Language
    *[W3C]: World Wide Web Consortium
    ````

The HTML specification is maintained by the W3C.

_Remember to locate the Markdown file containing the definitions outside of the_
`docs` _folder or MkDocs may complain about an unreferenced file._

## Admonitions / Message Boxes

Supported types are: `note`/`seealso`, `abstract`/`summary`/`tldr`, `info`/`todo`, `tip`/`hint`/`important`, `success`/`check`/`done`, `question`/`help`/`faq`, `warning`/`caution`/`attention`, `failure`/`fail`/`missing`, `danger`/`error`, `bug`, `quote`/`cite`.

To see more examples of boxes, see the [Message Boxes](../message_boxes) page

You can also embed code like this:

``` markdown
!!! note
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

    ``` python
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

    Nunc eu odio eleifend, blandit leo a, volutpat sapien. Phasellus posuere in
    sem ut cursus. Nullam sit amet tincidunt ipsum, sit amet elementum turpis.
    Etiam ipsum quam, mattis in purus vitae, lacinia fermentum enim.
```

!!! note
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

    ``` python
    def bubble_sort(items):
        for i in range(len(items)):
            for j in range(len(items) - 1 - i):
                if items[j] > items[j + 1]:
                    items[j], items[j + 1] = items[j + 1], items[j]
    ```

    Nunc eu odio eleifend, blandit leo a, volutpat sapien. Phasellus posuere in
    sem ut cursus. Nullam sit amet tincidunt ipsum, sit amet elementum turpis.
    Etiam ipsum quam, mattis in purus vitae, lacinia fermentum enim.

To create a collapsible box, use `???` instead of `!!!`:

```
??? note
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.
```

??? note
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.


## Buttons
``` markdown
[Click Me](#){: .md-button }
[No, Click Me!](#){: .md-button .md-button--primary }
```

[Click Me](#){: .md-button }
[No, Click Me!](#){: .md-button .md-button--primary }

## Code blocks
See [Supported languages](#supported-languages) at the end of the page for specific options you can add to highlight your code block.

```` markdown
``` python
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````

``` python
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

### Display line numbers
```` markdown
``` python linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````

``` python linenums="1"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

### Highlighting specific lines

```` markdown
``` python hl_lines="2 4"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```
````

``` python hl_lines="2 4"
def bubble_sort(items):
    for i in range(len(items)):
        for j in range(len(items) - 1 - i):
            if items[j] > items[j + 1]:
                items[j], items[j + 1] = items[j + 1], items[j]
```

### Highlighting inline code
``` markdown
The `#!python range()` function is used to generate a sequence of numbers.
```
The `#!python range()` function is used to generate a sequence of numbers.

## Keyboard Keys
``` markdown
++ctrl+alt+del++
```

++ctrl+alt+del++


## Tabbed content
```` markdown
=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```
````

=== "C"

    ``` c
    #include <stdio.h>

    int main(void) {
      printf("Hello world!\n");
      return 0;
    }
    ```

=== "C++"

    ``` c++
    #include <iostream>

    int main(void) {
      std::cout << "Hello world!" << std::endl;
      return 0;
    }
    ```

You can also tab lists in this way:

```
=== "Unordered list"

    * Sed sagittis eleifend rutrum
    * Donec vitae suscipit est
    * Nulla tempor lobortis orci

=== "Ordered list"

    1. Sed sagittis eleifend rutrum
    2. Donec vitae suscipit est
    3. Nulla tempor lobortis orci
```

=== "Unordered list"

    * Sed sagittis eleifend rutrum
    * Donec vitae suscipit est
    * Nulla tempor lobortis orci

=== "Ordered list"

    1. Sed sagittis eleifend rutrum
    2. Donec vitae suscipit est
    3. Nulla tempor lobortis orci

## Footnotes
```
Lorem ipsum[^1] dolor sit amet, consectetur adipiscing elit.[^2]

[^1]: Lorem ipsum dolor sit amet, consectetur adipiscing elit.
[^2]: https://loremipsum.io/
```

Lorem ipsum[^1] dolor sit amet, consectetur adipiscing elit.[^2]

[^1]: Lorem ipsum dolor sit amet, consectetur adipiscing elit.
[^2]: https://loremipsum.io/

## Formatting
### Highlighting changes

``` markdown
Text can be {--deleted--} and replacement text {++added++}. This can also be
combined into {~~one~>a single~~} operation. {==Highlighting==} is also
possible {>>and comments can be added inline<<}.

{==

Formatting can also be applied to blocks, by putting the opening and closing
tags on separate lines and adding new lines between the tags and the content.

==}
```

Text can be {--deleted--} and replacement text {++added++}. This can also be
combined into {~~one~>a single~~} operation. {==Highlighting==} is also
possible {>>and comments can be added inline<<}.

{==

Formatting can also be applied to blocks, by putting the opening and closing
tags on separate lines and adding new lines between the tags and the content.

==}

### Subscripts and Superscripts
``` markdown
* H~2~0
* A^T^A
```

* H~2~0
* A^T^A

### Images

``` markdown
![Placeholder](https://via.placeholder.com/150){: align=left width=50 }
```

![Placeholder](https://via.placeholder.com/150){: align=left width=50 }

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor massa, nec semper lorem quam in massa.

#### Image captions

```html
<figure>
  <img src="https://via.placeholder.com/150" width="50" />
  <figcaption>Image caption</figcaption>
</figure>
```

<figure>
  <img src="https://via.placeholder.com/150" width="50" />
  <figcaption>Image caption</figcaption>
</figure>

#### Image lazy-loading

``` markdown
![Placeholder](https://via.placeholder.com/150){: loading=lazy width=50 }
```

![Placeholder](https://via.placeholder.com/150){: loading=lazy width=50 }

### Lists

#### unordered
``` markdown
* Nulla et rhoncus turpis. Mauris ultricies elementum leo. Duis efficitur
  accumsan nibh eu mattis. Vivamus tempus velit eros, porttitor placerat nibh
  lacinia sed. Aenean in finibus diam.

    * Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
    * Nam vulputate tincidunt fringilla.
    * Nullam dignissim ultrices urna non auctor.
```

* Nulla et rhoncus turpis. Mauris ultricies elementum leo. Duis efficitur
  accumsan nibh eu mattis. Vivamus tempus velit eros, porttitor placerat nibh
  lacinia sed. Aenean in finibus diam.

    * Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
    * Nam vulputate tincidunt fringilla.
    * Nullam dignissim ultrices urna non auctor.

#### ordered lists

``` markdown
1. Vivamus id mi enim. Integer id turpis sapien. Ut condimentum lobortis
  sagittis. Aliquam purus tellus, faucibus eget urna at, iaculis venenatis
  nulla. Vivamus a pharetra leo.

    1. Vivamus venenatis porttitor tortor sit amet rutrum. Pellentesque aliquet
      quam enim, eu volutpat urna rutrum a. Nam vehicula nunc mauris, a
      ultricies libero efficitur sed.

    2. Morbi eget dapibus felis. Vivamus venenatis porttitor tortor sit amet
      rutrum. Pellentesque aliquet quam enim, eu volutpat urna rutrum a.

        1. Mauris dictum mi lacus
        2. Ut sit amet placerat ante
        3. Suspendisse ac eros arcu
```

1. Vivamus id mi enim. Integer id turpis sapien. Ut condimentum lobortis
  sagittis. Aliquam purus tellus, faucibus eget urna at, iaculis venenatis
  nulla. Vivamus a pharetra leo.

    1. Vivamus venenatis porttitor tortor sit amet rutrum. Pellentesque aliquet
      quam enim, eu volutpat urna rutrum a. Nam vehicula nunc mauris, a
      ultricies libero efficitur sed.

    2. Morbi eget dapibus felis. Vivamus venenatis porttitor tortor sit amet
      rutrum. Pellentesque aliquet quam enim, eu volutpat urna rutrum a.

        1. Mauris dictum mi lacus
        2. Ut sit amet placerat ante
        3. Suspendisse ac eros arcu

#### definition lists
``` markdown
`Lorem ipsum dolor sit amet`
:   Sed sagittis eleifend rutrum. Donec vitae suscipit est. Nullam tempus
    tellus non sem sollicitudin, quis rutrum leo facilisis.

`Cras arcu libero`
:   Aliquam metus eros, pretium sed nulla venenatis, faucibus auctor ex. Proin
    ut eros sed sapien ullamcorper consequat. Nunc ligula ante.

    Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
    Nam vulputate tincidunt fringilla.
    Nullam dignissim ultrices urna non auctor.
```

`Lorem ipsum dolor sit amet`
:   Sed sagittis eleifend rutrum. Donec vitae suscipit est. Nullam tempus
    tellus non sem sollicitudin, quis rutrum leo facilisis.

`Cras arcu libero`
:   Aliquam metus eros, pretium sed nulla venenatis, faucibus auctor ex. Proin
    ut eros sed sapien ullamcorper consequat. Nunc ligula ante.

    Duis mollis est eget nibh volutpat, fermentum aliquet dui mollis.
    Nam vulputate tincidunt fringilla.
    Nullam dignissim ultrices urna non auctor.


#### tasklists

``` markdown
* [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
* [ ] Vestibulum convallis sit amet nisi a tincidunt
    * [x] In hac habitasse platea dictumst
    * [x] In scelerisque nibh non dolor mollis congue sed et metus
    * [ ] Praesent sed risus massa
* [ ] Aenean pretium efficitur erat, donec pharetra, ligula non scelerisque
```

* [x] Lorem ipsum dolor sit amet, consectetur adipiscing elit
* [ ] Vestibulum convallis sit amet nisi a tincidunt
    * [x] In hac habitasse platea dictumst
    * [x] In scelerisque nibh non dolor mollis congue sed et metus
    * [ ] Praesent sed risus massa
* [ ] Aenean pretium efficitur erat, donec pharetra, ligula non scelerisque

## Math
To display Math if needed, you should use MathJax formating, a nice how to can be found [here](https://math.meta.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).

_To see how any formula was written, right-click on the expression and choose "Show Math As > TeX Commands", the '$' will not display_

**Examples**:

```
$$x^2 + y^2 = z^2$$

$$L_i = {1 \over N} \sum_i \sum_{j \ne y_i} [ \max(0, f(x_i;W)_j - f(x_i;W) + \Delta) ]$$

When \(a \ne 0\), there are two solutions to \(ax^2 + bx + c = 0\) and they are $$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

```

$$x^2 + y^2 = z^2$$

$$L_i = {1 \over N} \sum_i \sum_{j \ne y_i} [ \max(0, f(x_i;W)_j - f(x_i;W) + \Delta) ]$$

When \(a \ne 0\), there are two solutions to \(ax^2 + bx + c = 0\) and they are $$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$


## Supported languages
Pygments supports an ever-growing range of languages.

| Programming languages | Template languages | Other markup |
|--|--|--|
| ActionScript | Angular templates | Apache config files |
| Ada | Cheetah templates | Apache Pig |
| Agda (incl. literate) | ColdFusion | BBCode |
| Alloy | Django / Jinja templates | Cap’n Proto |
| AMPL | ERB (Ruby templating) | CapDL |
| ANTLR | Evoque | CMake |
| APL | Genshi (the Trac template language) | Csound scores |
| AppleScript | Handlebars | CSS |
| Assembly (various) | JSP (Java Server Pages) | Debian control files |
| Asymptote | Liquid | Diff files |
| Augeas | Mako (the Myghty successor) | Dockerfiles |
| AutoIt | Myghty (the HTML::Mason based framework) | DTD |
| Awk | Slim | E-mail headers |
| BARE | Smarty templates (PHP templating) | EBNF |
| BBC Basic | Tea | Extempore |
| Befunge | Twig | Flatline |
| BlitzBasic |  | Gettext catalogs |
| Boa |  | Gnuplot script |
| Boo |  | Groff markup |
| Boogie |  | Hexdumps |
| BrainFuck |  | HTML |
| C, C++ (incl. dialects like Arduino) |  | HTTP sessions |
| C# |  | IDL |
| Chapel |  | Inform |
| Charm++ CI |  | INI-style config files |
| Cirru |  | IRC logs (irssi style) |
| Clay |  | Isabelle |
| Clean |  | JSGF notation |
| Clojure |  | JSON, JSON-LD |
| CoffeeScript |  | Lean theorem prover |
| ColdFusion |  | Lighttpd config files |
| Common Lisp |  | Linux kernel log (dmesg) |
| Component Pascal |  | LLVM assembly |
| Coq |  | LSL scripts |
| Croc (MiniD) |  | Makefiles |
| Cryptol (incl. Literate Cryptol) |  | MoinMoin/Trac Wiki markup |
| Crystal |  | MQL |
| Cypher |  | MySQL |
| Cython |  | NCAR command language |
| D |  | Nginx config files |
| Dart |  | Nix language |
| DCPU-16 |  | Notmuch |
| Delphi |  | NSIS scripts |
| Devicetree |  | PEG |
| Dylan (incl. console) |  | POV-Ray scenes |
| Eiffel |  | PromQL |
| Elm |  | Puppet |
| Emacs Lisp |  | QML |
| Email |  | Ragel |
| Erlang (incl. shell sessions) |  | Redcode |
| Execline |  | ReST |
| Ezhil |  | Roboconf |
| F* |  | Robot Framework |
| F# |  | RPM spec files |
| Factor |  | Rql |
| Fancy |  | RSL |
| Fantom |  | Scdoc |
| Fennel |  | Sieve |
| FloScript |  | Singularity |
| Fortran |  | SPARQL |
| FreeFEM++ |  | SQL, also MySQL, SQLite |
| GAP |  | Squid configuration |
| GDScript |  | TADS 3 |
| Gherkin (Cucumber) |  | Terraform |
| GLSL shaders |  | TeX |
| GnuCOBOL (OpenCOBOL) |  | Thrift |
| Golo |  | TNT |
| Gosu |  | TOML |
| Groovy |  | Treetop grammars |
| Haskell (incl. Literate Haskell) |  | USD (Universal Scene Description) |
| Haxe |  | Varnish configs |
| HLSL shaders |  | VGL |
| HSpec |  | Vim Script |
| Hy |  | WDiff |
| IDL |  | Web IDL |
| Idris (incl. Literate Idris) |  | Windows batch files |
| Igor Pro |  | Windows Registry files |
| Io |  | XML |
| Jags |  | XSLT |
| Jasmin |  | YAML |
| Java |  | YANG |
| JavaScript |  |  |
| Jcl |  |  |
| Julia |  |  |
| Kotlin |  |  |
| Lasso (incl. templating) |  |  |
| Limbo |  |  |
| LiveScript |  |  |
| LLVM MIR |  |  |
| Logos |  |  |
| Logtalk |  |  |
| Lua |  |  |
| Mathematica |  |  |
| Matlab |  |  |
| MiniScript |  |  |
| Modelica |  |  |
| Modula-2 |  |  |
| Monkey |  |  |
| Monte |  |  |
| MoonScript |  |  |
| Mosel |  |  |
| MuPad |  |  |
| NASM |  |  |
| Nemerle |  |  |
| NesC |  |  |
| NewLISP |  |  |
| Nim |  |  |
| Nit |  |  |
| Notmuch |  |  |
| NuSMV |  |  |
| Objective-C |  |  |
| Objective-J |  |  |
| OCaml |  |  |
| Octave |  |  |
| Opa |  |  |
| ParaSail |  |  |
| Pawn |  |  |
| Perl 5 |  |  |
| PHP |  |  |
| Pike |  |  |
| Pointless |  |  |
| Pony |  |  |
| PostScript |  |  |
| PovRay |  |  |
| PowerShell |  |  |
| Praat |  |  |
| Prolog |  |  |
| Python 2.x and 3.x (incl. console sessions and tracebacks) |  |  |
| QBasic |  |  |
| Racket |  |  |
| Raku a.k.a. Perl 6 |  |  |
| ReasonML |  |  |
| REBOL |  |  |
| Red |  |  |
| Redcode |  |  |
| Rexx |  |  |
| Ride |  |  |
| Ruby (incl. irb sessions) |  |  |
| Rust |  |  |
| S, S-Plus, R |  |  |
| Scala |  |  |
| Scdoc |  |  |
| Scheme |  |  |
| Scilab |  |  |
| SGF |  |  |
| Shell scripts (Bash, Tcsh, Fish) |  |  |
| Shen |  |  |
| Silver |  |  |
| Slash |  |  |
| Slurm |  |  |
| Smalltalk |  |  |
| SNOBOL |  |  |
| Snowball |  |  |
| Solidity |  |  |
| SourcePawn |  |  |
| Stan |  |  |
| Standard ML |  |  |
| Stata |  |  |
| SuperCollider |  |  |
| Swift |  |  |
| Swig |  |  |
| Tcl |  |  |
| Tera Term language |  |  |
| TypeScript |  |  |
| TypoScript |  |  |
| Unicon |  |  |
| Urbiscript |  |  |
| USD |  |  |
| Vala |  |  |
| VBScript |  |  |
| Verilog, SystemVerilog |  |  |
| VHDL |  |  |
| Visual Basic.NET |  |  |
| Visual FoxPro |  |  |
| Whiley |  |  |
| XQuery |  |  |
| Xtend |  |  |
| Zeek |  |  |
| Zephir |  |  |
| Zig |  |  |
