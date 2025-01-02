# Flavor

Glagolica supports default CommonMark flavor alongside [GFM](https://github.github.com/gfm).
This is the most known flavor that most developers are familiar with.

Additionally we provide non-standard HTML elements to make hard things simpler.

## Blockquotes

We also include [extended blockquotes](https://github.com/orgs/community/discussions/16925):

```
> [!NOTE]
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Crucial information necessary for users to succeed.

> [!WARNING]
> Critical content demanding immediate user attention due to potential risks.

> [!CAUTION]
> Negative potential consequences of an action.
```

This decision is made to be backwards compatible with markdown renderer on github.

## Steps

To introduce documentation user to a step-by-step guide, Glagolica supports adding step notation:

<!-- prettier-ignore-start -->
```md
<steps>
  <step>
    ### This is the first step
    It involves certain actions:

    ![Do as stated in this image](/dummy.png)
  </step>
  <step>
    ### This is the second step
    We do some other manipulations here.
  </step>

  <step>
    ### This is the third step.
  </step>
  <step>
    Last step without a heading
  </step>
</steps>
```
<!-- prettier-ignore-end -->

### TOC

To render Table of Contents, developers do not need to add links in the nested list, instead they can use following syntax:

```md
<toc>
<!-- or <toc /> -->
```

### Code Blocks

Code blocks are defined using the same exact syntax documented by CommonMark:

````
```
print("Code here")
```
````

#### Tabs

To make your code blocks grouped by tabs, use `tabs` element:

<!-- prettier-ignore-start -->
````md
<tabs names="JavaScript, Python, Rust">
  ```js
  console.log("Hello, World!");
  ```

  ```py
  print("Hello, World!")
  ```

  ```rs
  fn main() {
    println!("Hello, World!");
  }
  ```
</tabs>
````
<!-- prettier-ignore-end -->

#### Highlighting

For code block highlighting, we provide extended syntax with parameters syntax similar to html/xml:

````md
```go highlight="3, 5-7"
package main

import "fmt"

func main() {
  fmt.Println("Hello, World!")
}
```
````

The code above highlights lines 3, 5, 6 & 7.

#### Diffs

We're using the same format documented for highlighting to represent code diffs:

````md
```gleam plusdiff="5" minusdiff="4"
import gleam/io

pub fn main() {
  io.println("Hello, Joe!");
  io.println("Hello, Joe!")
}
```
````

#### Line Numbers

To add line numeration provide `linenumbers` attribute to the code block:

````md
```kt linenumbers
fun main() {
  println("Hello, World!")
}
```
````

Now it will prepend numbers to the left side of the code block.
