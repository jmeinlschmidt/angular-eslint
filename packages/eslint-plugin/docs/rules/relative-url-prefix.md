<!--

  DO NOT EDIT.

  This markdown file was autogenerated using a mixture of the following files as the source of truth for its data:
  - ../../src/rules/relative-url-prefix.ts
  - ../../tests/rules/relative-url-prefix/cases.ts

  In order to update this file, it is therefore those files which need to be updated, as well as potentially the generator script:
  - ../../../../tools/scripts/generate-rule-docs.ts

-->

# `@angular-eslint/relative-url-prefix`

The ./ and ../ prefix is standard syntax for relative URLs; don't depend on Angular's current ability to do without that prefix. See more at https://angular.io/styleguide#style-05-04

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

```ts
@Component({
  styleUrls: ['./foo.css', 'bar.css', '../baz.scss', '../../test.css']
                           ~~~~~~~~~
})
class Test {}
```

```ts
@Component({
  templateUrl: 'foobar.html'
               ~~~~~~~~~~~~~
})
class Test {}
```

<br>

---

<br>

✅ - Examples of **correct** code for this rule:

```ts
@Component({
  styleUrls: [
    './foo.css',
    '../bar.css',
    '../../baz.scss',
    '../../../baz.sass',
    './../test.css',
    '.././angular.sass'
  ]
})
class Test {}
```

```ts
@Component({
  templateUrl: './foobar.html'
})
class Test {}
```

```ts
@Component({
  templateUrl: '../foobar.html'
})
class Test {}
```

```ts
@Component({
  templateUrl: '../../foobar.html'
})
class Test {}
```

```ts
@Component({
  templateUrl: '../../../foobar.html'
})
class Test {}
```

```ts
@Component({
  templateUrl: './../foobar.html'
})
class Test {}
```

```ts
@Component({
  templateUrl: '.././foobar.html'
})
class Test {}
```