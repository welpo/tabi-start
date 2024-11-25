+++
title = "Hello World Project"
description = "A simple demo project showcasing tabi's project features"
weight = 1
template = "page.html"

[taxonomies]
tags = ["meta"]

[extra]
local_image = "img/profile.webp"
+++

A minimal project to demonstrate how project pages work in tabi. This template supports Markdown formatting, code blocks, and more.

{{ admonition(type="tip", text="The project image is set in the `[extra]` section of the page, as either `local_image` or `remote_image` (for an URL).") }}

#### [View Source](https://github.com/welpo/tabi-start){.centered-text}

## Features showcase

Here's what you can do with project pages:

- Add project descriptions
- Include code snippets
- Tag your projects
- Add images and media
- Link to external resources

## Sample Code

Here's a simple "Hello, World!" in different languages:

```python
print("Hello, World!")
```

```javascript
console.log("Hello, World!");
```

```rust
fn main() {
    println!("Hello, World!");
}
```

Feel free to delete this demo project when you're ready to add your own!
