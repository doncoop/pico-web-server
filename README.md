# Pico W Custom Start Page / Webserver

![homepage](https://i.redd.it/cbnzq36zj3601.gif)

## Introduction

This project is a fork of the great start page by Jaredk3nt which can be found [here](https://github.com/Jaredk3nt/homepage). I take no credit for it's functionality or style. This was used as a base to prove a Raspberry Pi Pico W could be used to host a custom start page running a webserver.

Other awesome startpages can be found on the [AwesomeStartpage](https://github.com/jnmcfly/awesome-startpage) GitHub repo.

## Hosting on a Pico W

To run a webserver on your Pico W you will need to install MicroPython. I recommend you follow the [Raspberry Pi](https://www.raspberrypi.com/news/how-to-run-a-webserver-on-raspberry-pi-pico-w/) tutorial.

After installing MicroPython, to host this startpage on a Raspberry Pi Pico W you will need all the files in this repo (bar this readme). You will need to copy or create them on your Pico W and then amend the SSID and password contained within the secrets.py file as a minimum.

## Customisation

### Customise Bookmarks

Bookmarks are now held in the `bookmarks.js` file for easy updating. `bookmarks` is an array of objects with a `title` and `links` property. The `title` defines what the header of the "bookmark section" box will be. `link` is an array of link objects each with a name and a url to link to.

> The way the site is currently styled bookmarks should always have a length of `4` if you want to have more sections you need to change the `width` property of the css class `bookmark-set`

### Customise Search Engine

You can change the search engine used by the search overlay by updating the url value stored in the `searchUrl` var in `index.html` to the correct string for your engine.

Examples:

- DuckDuckGo: `https://duckduckgo.com/?q=`
- Bing: `https://www.bing.com/search?q=`

### Customise Styling

Styles are handled through CSS variables. To update the colors you just need to change the variable definitions defined in `:root`.

| Variable           | default                    | description                                                                                                                |
| ------------------ | -------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `--bg`             | `#5f4b8b`                  | Defines the body background color                                                                                          |
| `--fg`             | `#ffffff`                  | Defines the primary foreground (text) colour for clock, weather, and titles                                                 |
| `--secondaryFg`    | `#b3b3b3`                  | Defines the foreground (text) colour for links                                                                              |
| `--containerBg`    | `#272727`                  | Defines the background colour of the boxes                                                                                  |
| `--searchBg`       | `--containerBg`            | Defines the background colour of the search overlay                                                                         |
| `--scrollbarColor` | `#3f3f3f`                  | Defines the colour of the custom scrollbars                                                                                 |
| `--fontFamily`     | `"Roboto Mono", monospace` | Defines the font used. To change to a custom font you will also have to import that font from whatever source is available |
