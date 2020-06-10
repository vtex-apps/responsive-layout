# Responsive Layout
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

Responsive Layout allows you to declare layout structures that will only be rendered in a specific screen-size breakpoint.

![responsive-layout-gif](https://user-images.githubusercontent.com/27777263/70263027-3a4d2180-1774-11ea-80b2-47c503eba75c.gif)

Now, you are able to use all blocks exported by the `responsive-layout` app. Check out the full list below:

| Block name     | Description                                     |
| -------------- | ----------------------------------------------- |
| `responsive-layout.desktop` | Builds a responsive layout for desktop devices.   |
| `responsive-layout.tablet` | Builds a responsive layout for tablet devices. | 
| `responsible-layout.phone` | Builds a responsive layout for phone devices. |
| `responsive-layout.mobile` | Builds a responsive layout for mobile devices, managing the tablet *and* phone breakpoints at the same time. |

Each of them have `composition: children`, which means that they expect to receive an array of `children` blocks to be rendered by them, if the current screen-size is right for their breakpoint.

## Configuration

1. Import the Responsive Layout app to your theme's dependencies on the `manifest.json`, for example:

```json
  "dependencies: {
    "vtex.responsive-layout": "0.x"
  }
```

2. Add the `responsive-layout` block into your theme. Here's an example:

```jsonc
  "store.custom#about-us": {
    "blocks": [
      "responsive-layout.desktop",
      "responsive-layout.tablet",
      "responsive-layout.phone"
      // If `tablet` and `phone` are equal, just use the "responsive-layout.mobile" block
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

## Customization 

No CSS Handles are available for the app customization.

<!-- DOCS-IGNORE:start -->

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="http://gabenna.io"><img src="https://avatars1.githubusercontent.com/u/4580524?v=4" width="100px;" alt=""/><br /><sub><b>Micael Pereira</b></sub></a><br /><a href="https://github.com/vtex-apps/responsive-layout/commits?author=micas06gua" title="Documentation">📖</a></td>
  </tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->
<!-- DOCS-IGNORE:end -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
