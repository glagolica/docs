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

### TOC

To render Table of Contents, developers do not need to add links in the nested list, instead they can use following syntax:

```md
<toc>
<!-- or <toc /> -->
```

### Code Blocks

// TODO

#### Tabs

// TODO

#### Highlighting

// TODO
