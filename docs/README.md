# VTEX Responsive Layout

Responsive-layout allows you to declare layout structures that will only be rendered in a specific screen-size breakpoint.

There are four blocks defined and exported by this app:

- `responsive-layout.desktop`
- `responsive-layout.mobile`
- `responsive-layout.tablet`
- `responsive-layout.phone`

Each of them have `composition: children`, which means that they expect to receive an array of `children` blocks to be rendered by them, if the current screen-size is right for their breakpoint.

## Blocks API

These blocks are defined by the interfaces below:

```json
  "responsive-layout.desktop": {
    "component": "ResponsiveLayoutDesktop",
    "composition": "children",
    "allowed": "*"
  },
  "responsive-layout.mobile": {
    "component": "ResponsiveLayoutMobile",
    "composition": "children",
    "allowed": "*"
  },
  "responsive-layout.tablet": {
    "component": "ResponsiveLayoutTablet",
    "composition": "children",
    "allowed": "*"
  },
  "responsive-layout.phone": {
    "component": "ResponsiveLayoutPhone",
    "composition": "children",
    "allowed": "*"
  }
```

Notice that you could use _any_ array of blocks as `children`, given that they are allowed by the `block` that is directly above your `responsive-layout`.

