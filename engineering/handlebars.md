# Handlebars Style Guide

## Table Of Contents

* [Quotes](#quotes)
* [Multiline expressions](#multiline-expressions)

## Quotes
Prefer double quotes to single quotes
```hbs
{{! good }}
<button {{action "doThing"}}>Do Thing</button>

{{! bad }}
<button {{action 'doThing'}}>Do Thing</button>
```

## Multi-line expressions

Multi-line expressions should specify attributes starting on the second
line, and should be indented to the start of the component or helper name. Block
style multi-line expressions should use two spaces and wrap the curly braces.

```hbs
{{! good }}
{{x-thing
  value=blah
  options=options
  label="thing"}}

{{! bad; this will be annoying to re-indent if the component is renamed }}
{{x-thing value=blah
          options=options
          label="thing"}}
  
{{! good }}
{{#x-thing
  value=blah
  options=options
  label="thing"
  as |some thing|
}}
  {{some (action thing)}}
{{/x-thing}}

{{! bad; this indentation is hard to follow }}
{{#x-thing
    value=blah
    options=options
    label="thing"
    as |some thing|}}
  {{some (action thing)}}
{{/x-thing}}
```
