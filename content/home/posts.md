---
# An instance of the Pages widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: portfolio

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 66

title: 'Blogs & Problem Solving'
subtitle:

content:
  # Page type to display. E.g. post, event, publication...
  page_type: posts
  # Choose how many pages you would like to display (0 = all pages)
  #count: 5
  # Filter on criteria
  #filters:
  # author: ""
  #  category: ""
  #  tag: ""
  #  exclude_featured: false
  #  exclude_future: false
  #  exclude_past: false
  #  publication_type: ""
  # Choose how many pages you would like to offset by
  # offset: 0
  # Page order: descending (desc) or ascending (asc) date.
  order: desc
  # Default filter index (e.g. 0 corresponds to the first `filter_button` instance below).
  # filter_default: 0

  # Filter toolbar (optional).
  # Add or remove as many filters (`filter_button` instances) as you like.
  # To show all items, set `tag` to "*".
  # To filter by a specific tag, set `tag` to an existing tag name.
  # To remove the toolbar, delete the entire `filter_button` block.
  filter_button:
  - name: All
    tag: '*'
  - name: Stat & Math
    tag: StatMath
  - name: Stuffs with R
    tag: R
  - name: Problem Corner
    tag: ProblemCorner


design:
  # Choose a view for the listings:
  #   1 = List
  #   2 = Compact
  #   3 = Card
  #   4 = Citation (publication only)
  view: 3
---
