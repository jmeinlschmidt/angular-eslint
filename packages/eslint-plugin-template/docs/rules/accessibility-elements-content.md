<!--

  DO NOT EDIT.

  This markdown file was autogenerated using a mixture of the following files as the source of truth for its data:
  - ../../src/rules/accessibility-elements-content.ts
  - ../../tests/rules/accessibility-elements-content/cases.ts

  In order to update this file, it is therefore those files which need to be updated, as well as potentially the generator script:
  - ../../../../tools/scripts/generate-rule-docs.ts

-->

# `@angular-eslint/template/accessibility-elements-content`

Ensures that the heading, anchor and button elements have content in it

- Type: suggestion
- Category: Best Practices

<br>

## Rule Options

The rule does not have any configuration options.

<br>

## Usage Examples

> The following examples are generated automatically from the actual unit tests within the plugin, so you can be assured that their behavior is accurate based on the current commit.

<br>

❌ - Examples of **incorrect** code for this rule:

```html
<h1 class="size-1"></h1>
~~~~~~~~~~~~~~~~~~~~~~~~
```

```html
<a href="#" [routerLink]="['route1']"></a>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
```

```html
<button></button>
~~~~~~~~~~~~~~~~~
```

<br>

---

<br>

✅ - Examples of **correct** code for this rule:

```html
<h1>Heading Content!</h1>
```

```html
<h2><app-content></app-content></h2>
```

```html
<h3 [innerHtml]="dangerouslySetHTML"></h3>
```

```html
<h4 [innerText]="text"></h4>
```

```html
<a>Anchor Content!</a>
```

```html
<a><app-content></app-content></a>
```

```html
<a [innerHTML]="dangerouslySetHTML"></a>
```

```html
<a [innerText]="text"></a>
```

```html
<a [outerHTML]="text"></a>
```

```html
<a aria-hidden></a>
```

```html
<button [attr.aria-hidden]="true"></button>
```

```html
<h5 [attr.aria-label]="text"></h5>
```

```html
<h6 title="text"></h6>
```