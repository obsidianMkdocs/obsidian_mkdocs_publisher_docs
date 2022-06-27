---
share: true
---

## [Mkdocs Publisher](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/)
### Quick installation tutorial
1. Click on [use this template](https://github.com/obsidianMkdocs/obsidian-mkdocs-publisher-template/generate)[^1]
2. Use the name of your choice
3. Set and edit the `configuration.yml` in the root of the repository.

### Plugin configuration

![](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/assets/upload/obs2mk-1.png)
![](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/assets/upload/obs2mk-2.png)

1. Folder reception settings : 
    - Reception settings : `YAML frontmatter`
    - Default folder : `docs/notes`
    - Choose your frontmatter key, same as in `configuration.yml`, by default: `category`
    - Root folder : `docs`
2. Workflow
    - Leave blank the GitHub actions
    - Auto-clean up : `TRUE`
    - Excluded folder : `docs/assets/logo, docs/assets/js, docs/assets/css`[^3]
2. Images settings : 
    - Turn on transfer image
    - Choose `docs/assets/img`
3. Folder note : `True`

The files (and the image) will be sent on your GitHub repository template, in the specified folder. The conversion will be done by the [github actions](https://github.com/Mara-Li/obsidian-mkdocs-publisher-template/blob/main/.github/workflows/ci.yml) when the branch were merged. 

### Useful informations
#### Links
- [Obsidian Plugin](https://github.com/obsidianMkdocs/obsidian-github-publisher)
- [Python package](https://github.com/obsidianMkdocs/obsidian-mkdocs-publisher-python)
- [Template](https://github.com/obsidianMkdocs/obsidian-mkdocs-publisher-template)

#### How to...
- [Configure the blog](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/documentation/create%20the%20blog/)
- [Customize the blog](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/documentation/blog%20customization/)
- [Copy the link ?](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/documentation/useful%20plugins/#metacopy)
- [Update the template](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/documentation/Q%26A/#2-update-the-template)

#### Support
- [x] Wikilinks (`[[Links]]`)
- [x] File transclusion/embed, both wikilinks and markdown links
- [x] Obsidian callout and custom callout
- [x] Folder notes and their citation
- [x] Custom attributes
- [x] Sharing state and custom folder hierarchy.
- [x] Mobile and desktop
- [x] File mini preview on Hover

#### Limitations
- No plugins (dataview...)
- No graph view
- You need to have a clean tree structure with unique name file. No worry about the display in blog ; the `title` key in frontmatter will change it, so you can have a `ezarezozre` name and use a good title like `reading book`. 
-  I prefer to encourage you to use the `shortlinks` option in obsidian’s link option. 
- Obs2mk will don’t move the file if you change the `category` value : you need to manually delete it to prevent duplicate. 

---
## [Digital Garden](https://github.com/TuanManhCao/digital-garden)

![](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/assets/upload/digital-garden-1.png)
![](https://obsidianmkdocs.github.io/obsidian_mkdocs_publisher_docs/assets/upload/digital-garden-2.png)

1. Folder reception settings : 
    - Reception settings : `Obsidian Path`
    - Default folder : `posts`
2. Workflow : 
    - Leave blank
    - Turn on autoclean
3. Images settings :
    - Transfer image on true
    - Default folder : `posts/Attachments`