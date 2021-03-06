---
id: results-per-page
title: ResultsPerPage
---

`ResultsPerPage` renders a list of the possible number of results per page.

The component is **not** displayed while executing the search query or if there are no results.

## Usage

```jsx
<ResultsPerPage
  values={[{text: "Ten", value: 10}, {text: "Twenty", value: 20}]}
/>
```

## Props

* **values** `Array`

  A list of possible values, where each value has the format `{ text: "Fifty", value: 50 }`.

* **renderElement** `function` *optional*

  An optional function to override the default rendered component.

- **label** `function` _optional_

  An optional function to wrap the component with a prefix and suffix string. <br />
  E.g. `label={(cmp) => <> Show {cmp} results per page</>}`

## Usage when overriding template

```jsx
<ResultsPerPage renderElement={renderResultsPerPage} />
```

The function `renderElement` is called every time results or currentSize change.

```jsx
renderResultsPerPage = (currentSize, options, onValueChange) => {
  const _options = options.map(option => <li onClick={() => {onValueChange(option.value)}}>{option.text}</li>);
  return <ul>{this._options}</ul>;
}
```

### Parameters

* **currentSize** `String`

  The current value of the `size` `query` state.

* **options** `Array`

  The options passed as prop to the component.

* **onValueChange** `function`

  The function to call when the user changes the number of results per page to change the `query` state. `onValueChange(newValue)`
