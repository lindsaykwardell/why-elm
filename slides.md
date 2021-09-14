---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# Elm 

## A *delightful* Programming Language
## for *reliable* web applications

<img src="/logo.png" class="w-64 m-auto pt-4">

---

# What is Elm?

<img src="/logo.png" class="w-32 absolute top-5 right-5">

<div class="text-2xl">

<v-clicks>

- Functional Programming Language
- Compiles to JavaScript
- Statically typed
- Immutable data
- Pure functions
- No null/undefined/exceptions

</v-clicks>

</div>

<style scoped>
li {
  padding: 0.5rem 0;
}
</style>

---

<table>
  <thead>
    <tr>
      <th class="text-blue-500">JavaScript</th>
      <th class="text-green-500">Elm</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <v-clicks>
        <td>npm/yarn</td>
        <td>Built in</td>
      </v-clicks>
    </tr>
    <tr>
      <v-clicks>
        <td>React/Angular/Vue</td>
        <td>Built in</td>
      </v-clicks>
    </tr>
    <tr>
      <v-clicks>
        <td>Redux/NgRx/Vuex</td>
        <td>Built in</td>
      </v-clicks>
    </tr>
    <tr>
      <v-clicks>
        <td>Immutable.js/Object.freeze/etc</td>
        <td>Built in</td>
      </v-clicks>
    </tr>
    <tr>
      <v-clicks>
        <td>TypeScript</td>
        <td>Built in</td>
      </v-clicks>
    </tr>
    <tr>
      <v-clicks>
        <td>Webpack/Rollup/etc</td>
        <td>Built in</td>
      </v-clicks>
    </tr>
  </tbody>
</table>

<style scoped>
th {
  font-size: 2rem;
}

td:first-child {
  @apply bg-blue-900;
}

td:last-child {
  @apply bg-green-900;
}

td {
  width: 50%;
  padding: 1.5rem 0;
  text-align: center;
}

th {
  text-align: center;
}
</style>

---

# What makes it delightful?

<img src="/logo.png" class="w-32 absolute top-5 right-5">

<div class="text-2xl">

<v-clicks>

- Helpful error messages 😊
- No runtime exceptions 🤯
- Performant ⚡️
- Enforced semantic versioning 🎉

</v-clicks>

</div>

<style scoped>
li {
  padding: 0.5rem 0;
}
</style>

---

![](/typo.png)

---

![](/if-type.png)

---

![](/truthiness.png)

---

![](/concat.png)

---

# The Elm Architecture

<div class="bg-white w-2/3 m-auto flex justify-center">

![](https://guide.elm-lang.org/architecture/buttons.svg)

</div>

<div class="flex justify-around p-1">

## Model

## View

## Update

</div>

---

```elm {1-27|1-5|7|9-18|9|11-18|14-15|17-18|20-25|27}
module Main exposing (..)

import Browser
import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)

init = 0

type Msg = Increment | Decrement

update : Msg -> Model -> Model
update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1

view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (String.fromInt model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]

main = Browser.sandbox { init = init, update = update, view = view }
```

---

<div class="flex justify-center">

![](/elm-ui.png)

</div>

---

<div class="flex justify-center">

![](/elm-gql.png)

</div>

---
class: text-center
---

# Learn More

<hr class="my-6">

<v-clicks>

- https://guide.elm-lang.org/
- https://elmprogramming.com/
- https://ellie-app.com/new
- https://www.manning.com/books/elm-in-action
- https://github.com/lindsaykwardell/vite-elm-template

</v-clicks>

<v-clicks>

<div class="text-xs">

Credit to Mario Rogic for [example slides](https://docs.google.com/presentation/d/14rYuf7BzCZj8qjxGGRWpT1YVWdo_rG-FFiwNSEmFBV4/edit#slide=id.g76b8572296_0_0)

</div>

</v-clicks>
  
<style scoped>
li {
  padding: 1rem;
  text-align: left;
}
</style>