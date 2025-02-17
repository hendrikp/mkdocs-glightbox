# MkDocs GLightbox

<p align="center">
<a target="_blank" href="https://pypi.org/project/mkdocs-glightbox"><img src="https://img.shields.io/pypi/v/mkdocs-glightbox.svg" alt="PyPI version"/></a>
<a target="_blank" href="https://pypi.org/project/mkdocs-glightbox"><img src="https://img.shields.io/pypi/dm/mkdocs-glightbox.svg" alt="PyPI downloads"/></a>
<a target="_blank" href="https://codecov.io/gh/blueswen/mkdocs-glightbox"><img src="https://codecov.io/gh/blueswen/mkdocs-glightbox/branch/main/graph/badge.svg?token=KAJS3NU81H" alt="Codecov"/></a>
</p>

A MkDocs plugin supports image lightbox with [GLightbox](https://github.com/biati-digital/glightbox).

GLightbox is a pure javascript lightbox library with mobile support.

[Live demo](https://blueswen.github.io/mkdocs-glightbox/) with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).

## Dependency

1. Python Package
   1. beautifulsoup4>=4.11.1
2. GLightbox javascript file and CSS file
   1. GLightbox==3.2.0

## Usage

1. Install the plugin from PyPI

    ```bash
    pip install mkdocs-glightbox
    ```

2. Add ```glightbox``` plugin to your mkdocs.yml plugins sections:

    ```yaml
    plugins:
       - glightbox
    ```

3. All images will be added to the lightbox effect automatically, except images in an anchor tag and emoji images from [pymdown-extensions](https://facelessuser.github.io/pymdown-extensions/extensions/emoji/).

4. You may customize the plugin by passing options in mkdocs.yml:

    ```yaml
    plugins:
       - glightbox:
           touchNavigation: true
           loop: false
           effect: zoom
           slide_effect: slide
           width: 100%
           height: auto
           zoomable: true
           draggable: true
           skip_classes:
             - custom-skip-class-name
           auto_caption: false
           caption_position: bottom
    ```

    | Option           | Default | Description                                                                                          |
    | ---------------- | ------- | ---------------------------------------------------------------------------------------------------- |
    | touchNavigation  | true    | Enable or disable the touch navigation (swipe).                                                      |
    | loop             | false   | Loop slides on end.                                                                                  |
    | effect           | zoom    | Name of the effect on lightbox open. (zoom, fade, none)                                              |
    | slide_effect     | slide   | Name of the effect on lightbox slide. (slide, zoom, fade, none)                                      |
    | width            | 100%    | Width for inline elements and iframes. You can use any unit for example 90% or 100vw for full width. |
    | height           | auto    | Height for inline elements and iframes. You can use any unit for example 90%, 100vh or auto.         |
    | zoomable         | true    | Enable or disable zoomable images.                                                                   |
    | draggable        | true    | Enable or disable mouse drag to go prev and next slide.                                              |
    | skip_classes     | [ ]     | Disable lightbox of those image with specific custom class name.                                     |
    | auto_caption     | false   | Enable or disable using alt of image as caption title automatically.                                 |
    | caption_position | bottom  | Default captions position. (bottom, top, left, right)                                                |

    Check more options information on [GLightbox Docs](https://github.com/biati-digital/glightbox#lightbox-options).

5. For more flexibility, you can disable the lightbox with a [specific image](https://blueswen.github.io/mkdocs-glightbox/disable/image/) or a [specific page](https://blueswen.github.io/mkdocs-glightbox/disable/page/).
6. Support lightbox image caption, check more details on [Caption](https://blueswen.github.io/mkdocs-glightbox/caption/caption/).
7. Support grouping images as galleries, check more details on [Gallery](https://blueswen.github.io/mkdocs-glightbox/gallery/gallery/).

## How it works

1. Copy GLightbox script file into `site/assets/javascripts/` directory and CSS file into `site/assets/stylesheets/` directory
2. Import GLightbox script and CSS file and add javascript code on each page excluded disabled pages
3. Search all image tags and warp with an anchor tag for GLightbox excluded images with skip class or already warped with an anchor tag

## License

This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/Blueswen/mkdocs-glightbox/blob/main/LICENSE) file for details.
