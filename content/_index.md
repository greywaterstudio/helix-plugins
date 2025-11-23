---
title: "Plugin Index"
description: ''
layout: single
---

<div class="search js-only">
  <input type="text" id="search" placeholder="Search Plugins...">
</div>

<script>
// @license magnet:?xt=urn:btih:5ac446d35272cc2e4e85e4325b146d0b7ca8f50c&dn=unlicense.txt Unlicense

document.addEventListener("DOMContentLoaded", () => {
  for (e of document.getElementsByClassName("js-only")) {
    e.classList.remove("js-only");
  }

  const plugins = document.querySelectorAll("#artlist li");
  const search = document.getElementById("search");
  const oldheading = document.getElementById("newest-plugins");
  const clearSearch = document.getElementById("clear-search");
  const artlist = document.getElementById("artlist");

  search.addEventListener("input", () => {
    // grab search input value
    const searchText = search.value.toLowerCase().trim().normalize('NFD').replace(/\p{Diacritic}/gu, "");
    const searchTerms = searchText.split(" ");
    const hasFilter = searchText.length > 0;

    artlist.classList.toggle("list-searched", hasFilter);
    oldheading.classList.toggle("hidden", hasFilter);

    plugins.forEach(plugin => {
      const searchString = `${plugin.textContent} ${plugin.dataset.tags}`.toLowerCase().normalize('NFD').replace(/\p{Diacritic}/gu, "");
      const isMatch = searchTerms.every(term => searchString.includes(term));

      plugin.hidden = !isMatch;
      plugin.classList.toggle("matched-plugin", hasFilter && isMatch);
    })
  })

  clearSearch.addEventListener("click", () => {
    search.value = "";
    plugins.forEach(plugin => {
      plugin.hidden = false;
      plugin.classList.remove("matched-plugin");
    })

    artlist.classList.remove("list-searched");
    oldheading.classList.remove("hidden");
  })
})
// @license-end
</script>

## Newest Plugins

{{< artlist >}}

## Browse by Category

{{< tagcloud >}}

## Add Your Plugins

New plugins can be submitted [on Github](https://github.com/greywaterstudio/helix-plugins).
Just make a pull request following the submission instructions and it will be added to this site.
