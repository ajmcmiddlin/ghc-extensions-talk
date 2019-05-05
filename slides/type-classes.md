# Type Classes

## Type classes in Haskell 2010

::: {.left}

::: {.fragment data-fragment-index="1"}
[Section 4.3.1 of the standard](https://www.haskell.org/onlinereport/haskell2010/haskellch4.html#x10-750004.3) covers type classes.
:::

:::{.fragment data-fragment-index="2"}
To summarise, it says that a type class declaration must have the following form.
:::
:::

<pre class="nohighlight fragment" style="font-size: 1.1em" data-fragment-index="3"><code data-trim data-noescape>
<span class="fragment highlight-current-green" data-fragment-index="4">class</span> <span class="fragment highlight-current-green" data-fragment-index="5">cx =></span> <span class="fragment highlight-current-green" data-fragment-index="6">C</span> <span class="fragment highlight-current-green" data-fragment-index="7">u</span> <span class="fragment highlight-current-green" data-fragment-index="8">where cdecls</span>
</code></pre>

::: {.left}
<ul>
<span class="fragment highlight-current-green" data-fragment-index="4"><span class="fragment" data-fragment-index="4"><li>_must_ have the `class` keyword;</li></span></span>
<span class="fragment highlight-current-green" data-fragment-index="5"><span class="fragment" data-fragment-index="5"><li>_may_ have a context;</li></span></span>
<span class="fragment highlight-current-green" data-fragment-index="6"><span class="fragment" data-fragment-index="6"><li>_must_ have a class name;</li></span></span>
<span class="fragment highlight-current-green" data-fragment-index="7"><span class="fragment" data-fragment-index="7"><li>_must_ be parameterised over exactly one type; and</li></span></span>
<span class="fragment highlight-current-green" data-fragment-index="8"><span class="fragment" data-fragment-index="8"><li>_may_ declare one or more members.</li></span></span>
</ul>
:::

##

::: {.left}
Some examples
:::

<pre class="haskell"><code data-trim data-noescape>
<span class="fragment fade-in-then-semi-out">class Eq a => Ord a where
  compare :: a -> a -> Ordering
  ...</span>

<span class="fragment fade-in-then-semi-out">class Show a where
  show :: a -> String
  ...</span>

<span class="fragment fade-in-then-semi-out">class (Ord a, Show a) => ShOrd a</span>
</code></pre>

::: {.notes}
`ShOrd` doesn't have a body, but is useful to express a set of constraints using one constraint.
:::

## Type class instances in Haskell 2010

::: {.left}
::: {.fragment data-fragment-index="1"}
[Section 4.3.2 of the standard](https://www.haskell.org/onlinereport/haskell2010/haskellch4.html#x10-750004.3)
covers type class instance declarations.
:::

::: {.fragment data-fragment-index="2"}
In short, it says that a type class instance must have the following form.
:::
:::

<pre class="fragment no-highlight" style="font-size: 1em" data-fragment-index="3"><code data-trim data-noescape>
<span class="fragment highlight-current-green" data-fragment-index="4">instance</span> <span class="fragment highlight-current-green" data-fragment-index="5">cx =></span> <span class="fragment highlight-current-green" data-fragment-index="6">C</span> <span class="fragment highlight-current-green" data-fragment-index="7">(T u1 … uk)</span> <span class="fragment highlight-current-green" data-fragment-index="8">where { d }</span>
</code></pre>

::: {.left}
<ul>
<span class="fragment" data-fragment-index="4"><span class="fragment highlight-current-green" data-fragment-index="4"><li>_must_ start with the `instance` keyword;</li></span></span>
<span class="fragment" data-fragment-index="5"><span class="fragment highlight-current-green" data-fragment-index="5"><li>_may_ have a context;</li></span></span>
<span class="fragment" data-fragment-index="6"><span class="fragment highlight-current-green" data-fragment-index="6"><li>_must_ mention the class name;</li></span></span>
<span class="fragment" data-fragment-index="7"><span class="fragment highlight-current-green" data-fragment-index="7"><li>_must_ mention the type the instance is for; and</li></span></span>
<span class="fragment" data-fragment-index="8"><span class="fragment highlight-current-green" data-fragment-index="8"><li>_may_ contain definitions for the class's members.</li></span></span>
</ul>
:::

