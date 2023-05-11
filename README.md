# Lazy Vertical Grid Compose

Lazy Vertical Grid Compose is a custom Android Compose component written in Kotlin that allows for lazy loading and displaying of grid items in a vertical scrolling list. The component is designed to efficiently display a large number of items without sacrificing performance or memory.

## Features

- Lazy loading of items: Items are loaded as needed while scrolling, reducing memory usage and improving performance.
- Customizable grid layout: You can configure the number of columns and the spacing between items.
- Customizable loading and error states: You can provide your own Composables to display while loading or if an error occurs while loading data.
- Handles empty states: You can provide your own Composable to display when there are no items to show.

## Usage

To use Lazy Vertical Grid Compose in your Android project, follow these steps:

1. Add the Lazy Vertical Grid Compose library to your project's dependencies. You can do this by adding the following line to your `build.gradle` file:

```
implementation 'com.example.lazy-vertical-grid-compose:lazy-vertical-grid-compose:1.0.0'
```

2. In your Composable function, create a `LazyVerticalGrid` instance and provide it with the necessary parameters, including the number of columns, the spacing between items, and a lambda that will be called to load the items:

```
val items = (1..1000).toList() // Replace with your own list of items to display
LazyVerticalGrid(
    columns = 2,
    spacing = 16.dp,
    contentPadding = PaddingValues(horizontal = 16.dp, vertical = 8.dp),
    emptyState = { /* Composable to display when there are no items */ },
    loadingState = { /* Composable to display while loading */ },
    errorState = { /* Composable to display if an error occurs while loading */ },
    items = items,
    loadMoreItems = { /* Lambda to load more items */ },
    content = { item ->
        /* Composable to display each item */
    }
)
```

The `content` lambda will be called for each item in the list to display. You can replace the `items` list with your own list of items to display, and replace the `content` lambda with your own Composable that will be used to display each item.

The `loadMoreItems` lambda will be called when the user scrolls to the end of the list, allowing you to load more items as needed.

## Customization

Lazy Vertical Grid Compose provides several customization options:

- `columns`: The number of columns to display in the grid.
- `spacing`: The spacing between items in the grid.
- `contentPadding`: The padding around the grid.
- `emptyState`: A Composable to display when there are no items to show.
- `loadingState`: A Composable to display while loading items.
- `errorState`: A Composable to display if an error occurs while loading items.
- `items`: The list of items to display in the grid.
- `loadMoreItems`: A lambda to load more items as needed.
- `content`: A lambda that will be called for each item in the list to display.

You can customize these options to fit your specific use case. For example, you can adjust the number of columns or the spacing between items to better fit your UI design.

## License

Lazy Vertical Grid Compose is released under the Apache 2.0 license. See the `LICENSE` file for more information.