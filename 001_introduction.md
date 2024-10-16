---
layout: default
title: Introduction
number: 1
---
# Introduction

This is where you introduce your project to your audience. You should summarize briefly the topic you are working on. (250-350 words)

The following is sample text to show the capabilities of presenting text with various formatting (such as bold), different languages, adding footnotes, and images.[^1]

{% assign media = site.media_metadata | where_exp: "item", "item.name == 'EmperorNapoleon'" %}
{% include media.html pages=media %}


Voilà! Вуаля! שלום עולם! Ça va?
Ut scelerisque ultrices orci, nec egestas sem. Cras feugiat nulla eget efficitur tempus. Morbi at pulvinar odio. Duis tempus neque in efficitur iaculis. Nullam ornare erat ut elit convallis consectetur. Integer a pulvinar dolor. Interdum et malesuada fames ac ante ipsum primis in faucibus. Morbi semper mattis odio ac volutpat. Suspendisse placerat rhoncus ligula, in pretium turpis aliquam nec. Curabitur gravida pretium mauris, in vulputate mauris tristique in. Suspendisse id facilisis sem, et dapibus tortor. Sed nisl metus, commodo ornare tortor non, aliquam suscipit arcu.[^2]

Curabitur sed feugiat elit. Donec feugiat nisi volutpat magna venenatis volutpat. Fusce efficitur sapien dignissim, pretium dolor sit amet, placerat lectus. Quisque enim est, viverra ut sem id, eleifend imperdiet ipsum. Pellentesque imperdiet pretium dui, eu sodales quam iaculis id. Fusce tristique convallis hendrerit. Suspendisse id mauris est. Etiam accumsan nisl vel neque porttitor, nec finibus est vehicula. Aliquam quam sem, rutrum elementum tincidunt non, ultricies a urna. Sed commodo, magna sed dictum malesuada, nulla ligula efficitur nisl, sed condimentum mauris nisl non purus. Sed pulvinar maximus fringilla. Sed scelerisque imperdiet volutpat. Praesent ligula nisl, venenatis finibus pharetra at, luctus id neque. Proin a efficitur ex. Donec vitae enim quis arcu ullamcorper molestie.

[^1]: First example footnote. View other pages to see sample methods of working with Markdown.
[^2]: I copied this text from this [website](https://www.lipsum.com/feed/html) 