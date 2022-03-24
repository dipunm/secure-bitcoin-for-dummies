---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
title: Introduction
nav_order: 1
---

# Welcome
This site aims to be a well rounded guide to help newcomers to create their own secure self-custody setups.

As coined by Andreas Antonopoulos, “Not your keys 🔑, Not your bitcoin <span style="color: #F7931A; font-weight: bold;">₿</span>”.

# Pick your starting point

- [A visual guide to bitcoin vaults](/guides/visual-guide.md)
- [Setup a Vault](#)
  - [Setup a receive-only wallet](#)
  - [Setup an inheritance plan](#)
- [Setup a Spending Wallet](#)
- [Setup a Lightning Wallet](#)


- [Creating a secure wallet with your ColdCard](#)
- [Creating a secure wallet with TailsOS](#)


<ul class="posts">
  {% for post in page.categories.wallets %}
    <li>
      <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>