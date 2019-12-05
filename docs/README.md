# VTEX Responsive Layout

Responsive-layout allows you to declare layout structures that will only be rendered in a specific screen-size breakpoint.

There are four blocks defined and exported by this app:

- `responsive-layout.desktop`
- `responsive-layout.mobile`
- `responsive-layout.tablet`
- `responsive-layout.phone`

Each of them have `composition: children`, which means that they expect to receive an array of `children` blocks to be rendered by them, if the current screen-size is right for their breakpoint.

## Example usage

This is an example on how to use this:

```json
  "store.custom#about-us": {
    "blocks": [
      "responsive-layout.desktop",
      "responsive-layout.tablet",
      "responsive-layout.phone"
    ]
  },
  
  "responsive-layout.desktop": {
    "children": ["rich-text#desktop"]
  },
  "responsive-layout.tablet": {
    "children": ["rich-text#tablet"]
  },
  "responsive-layout.phone": {
    "children": ["rich-text#phone"]
  },

  "rich-text#desktop": {
    "props": {
      "text": "# This will only show up on desktop.",
      "blockClass": "title"
    }
  },
  "rich-text#tablet": {
    "props": {
      "text": "# This will only show up on tablet.",
      "blockClass": "title"
    }
  },
  "rich-text#phone": {
    "props": {
      "text": "# This will only show up on phone.",
      "blockClass": "title"
    }
  },
```

Notice that you could use _any_ array of blocks as `children`, given that they are allowed by the `block` that is directly above your `responsive-layout`.
