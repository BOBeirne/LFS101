- GNU Info System - standard [[documentation]] format 
- Alternative to [[man]], created by the [[GNU]] project
 
## [[man]] vs info

| Feature      | man                 | info                               |
| ------------ | ------------------- | ---------------------------------- |
| Format       | single page, linear | Hyperlinked sections (like a wiki) |
| Navigation   | Scroll up/down      | Jump between linked "nodes"        |
| Detail level | Often shorter       | Usually more comprehensive         |
| Age          | 70s (UNIX)          | 80s (GNU)                          |

## Basic usage

| COMMAND      | OUTPUT                    |
| ------------ | ------------------------- |
| info         | Browse all topics (index) |
| info command | info page for command     |
| info ls      | ls documentation          |

## Navigation

| KEY       | ACTION                  |
| --------- | ----------------------- |
| Space     | next page               |
| Backspace | previous page           |
| q         | quit                    |
| h         | help (all keys)         |
| /pattern  | search                  |
| n         | next node               |
| p         | previous node           |
| u         | up (parent section)     |
| Enter     | follow link under curso |
| l         | go back                 |
## nodes

- each topic is called a node, it's like a tree of web pages
- nodes are essentially sections and / or subsections in the [[Documentation]]

### Node navigation

| KEY   | ACTION                  |
| ----- | ----------------------- |
| n     | next node               |
| p     | previous node           |
| u     | up (parent section)     |
| Enter | follow link under curso |
| l     | go back                 |

## Menu items

| SYMBOL           | MEANING                     |
| ---------------- | --------------------------- |
| `*` at the start | menu item (clickable url)   |
| `::` at the end  | inline reference link       |
| `=>`             | points to current menu item |
