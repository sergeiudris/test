## the problem

- you want to have a very large document, but avoid header names collision
- painfully, github's markdown/rst/asciidoc do not allow to give a header a custom anchor id/link
- so, if you have
```markdown
## some header

or

== some header

or

***
some header
```
- you are stuck with github.com/link-to-doc#some-header 
- you cannot use raw `<h2 id="different-anchor">some-header</h2>` either, it still gets replaced with #some-header

## the hash approach/solution

---

```markdown
## First heading <sup><sup><sub>2020-09-05 <a name="235ffda" href="#235ffda">235ffda</a></sub></sup></sup> 
```

- renders as

## First heading <sup><sup><sub>2020-09-05 <a name="235ffda" href="#235ffda">235ffda</a></sub></sup></sup> 

---

- use headers freely, but append to each
```markdown
 <sup><sup><sub>2020-09-05 <a name="235ffda" href="#235ffda">235ffda</a></sub></sup></sup> 
```
- where a random hash gives any header uniqueness
- yes, it is a little taxing code-wise, but:
  - you get standard readable links to your header still, but with hash appended
  - if you rename the header and link breaks, user can use hash from old link to find the same header, but with new title
  - **because hash of every header in the documnet never-ever changes**, HOORAY!
  - or: **hash itself is a link(anchor)** and user can copy that link, which will never break
- at the cost of having a small superscript over every header, you get header-name-freedom and unique persistent links
- best of both worlds - auto generated header link and unique persisten hash for every single header



# test

<h1 id="my-custom-anchor-name">
  My Header Name
</h1>

- ad
- ff

## First heading <sup><sup><sub>2020-09-05 <a name="4dsdwd1c" href="#4dsdwd1c">4dsdwd1c</a></sub></sup></sup> 

- <span style="color:blue">some *blue* text</span>.
- a
- b


## First heading <sup><sup><sub>2020-09-05 <a name="53cf31" href="#53cf31">53cf31</a></sub></sup></sup>

- <span style="color:blue">some *blue* text</span>.
- a
- b

## First heading <sup><sup><sub>2020-09-05 <i>4dsdwd1c</i></sub></sup></sup>

- <span style="color:blue">some *blue* text</span>.
- a
- b

## First heading <sup><sup><sub>2020-09-05 7vwergv</sub></sup></sup>

- <span style="color:blue">some *blue* text</span>.
- a
- b

## First heading  <a class="anchor" aria-hidden="true" href="#first-heading-123" id="first-heading-123"><sup>link</sup></a>

- a
- b

## First heading <sup><sub>3y2ud</sub></sup>

- a
- b

## First heading <sup><sup>35tuh</sup></sup>

- a
- b

## First heading <sup><sub><sup><sub>32jfd</sub></sup></sub></sup>

- a
- b

## First heading <sup><sup><sub>8743hf</sub></sup></sup>

- a
- b



## First heading <sup><sub><sup>67123d</sup></sub></sup>

- a
- b

## First heading <sup>783fh</sup>

- a
- b

<h2 id="user-content-custom-asd">Second heading</h2>

- 1
- 2

<div id="user-content-custom-asd" class="h2">
  <a id="user-content-custom-asd" class="anchor" aria-hidden="true" href="#custom-asd">
    #
  </a>Second heading
</div>

## heading<a name="not-headin"></a>

- a
- a




## First heading <a href="#some-custom-anchor" id="some-custom-anchor">#</a>

- a
- b

<h2 id="custom-asd">Second heading</h2>

- a
- c

<a id="install-321321" ><h2>Install-qwe</h2></a>

- 1
- 2


<h2>Install-qwe<a name="install-321" /></h2>

- 1
- 2

## Install-qwe <a name="install-456" ></a>

- wer
- rtgrq

<a name="install-baz" />
<h2>Install-qwe</h2>

- 1
- 2

<h2 id="INSTALL123">Install</h2>
<p>blah blah</p>

<h2 name="user-content-foo--bar" id="user-content-foo--bar">
  <a id="user-content-foo" class="anchor" aria-hidden="true" href="#foo"></a>
  Heading123
</h2>

- asd
- few

<h2 name="foo--bar" id="foo--bar">Heading</h2>

- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar

<h2 name="foo--xyz" id="foo--xyz">Heading</h2>

- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
- foo
- bar
