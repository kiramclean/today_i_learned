# My Theme

This is a minimal blog theme for [hugo](http://gohugo.io). The theme is loosely based on [Hemingway2](https://github.com/beli3ver/hemingway2.git).

## Features

* Responsive & minimal design
* Google Analytics
* Basic [OpenGraph](http://ogp.me/) metadata support
* Option for social sharing icons on posts

## Getting Started

Clone this repository to your hugo theme directory.

## Configuration

Copy the `config.toml` in the root directory of your website. Overwrite the existing config file if necessary.

```toml
baseurl = "https://example.com"
languageCode = "en"
title = "Hu | Core"
theme = "Hucore"
copyright = "&copy; 2017 | Follow on <a href=\"https://twitter.com/kiraemclean\" target=\"_blank\">Twitter</a> ♥"
googleAnalytics = "trackingcode"

[taxonomies]
tag = "tags"
category = "categories"

[params]
description = "Your description here"
keywords = ["keyword 1", "keyword 2", "keyword 3"]
author = "Kira"
sharingicons = true

[[params.social]]
url = "https://github.com/mgjohansen"
fa_icon = "fa-github"

[[params.social]]
url = "https://gitlab.com/mgjohansen"
fa_icon = "fa-gitlab"

[[params.social]]
url = "https://twitter.com/mgjohansen"
fa_icon = "fa-twitter"

[[params.social]]
url = "https://linkedin.com/in/mgjohansen"
fa_icon = "fa-linkedin-square"

[[params.social]]
url = "/index.xml"
fa_icon = "fa-rss"

[[params.socialshare]]
url = "https://linkedin.com/in/mgjohansen"
fa_icon = "fa-linkedin-square"
```

## Build

```
hugo server
```

You can go to localhost:1313 and this theme should be visible.

## License

[MIT License](LICENSE.md).

## Author

[Kira McLean](https://github.com/kiramclean)

## Credits

Hucore is based on [Hemingway2](https://github.com/beli3ver/hemingway2.git) created by [Malte Kiefer](https://github.com/beli3ver).
