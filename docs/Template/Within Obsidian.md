---
share: true
---

>[!note] 
> The github actions will only convert hashtags and convertion to Admonition mkdocs callouts. Now, two mkdocs plugin handle this, so you don't need (normally) to use obs2mk in minimal configuration anymore. 
>
>The plugins are :
>- [Mkdocs Callouts](https://github.com/sondregronas/mkdocs-callouts)
>- [Custom Tags Attributes](https://github.com/Mara-Li/mkdocs-custom-tags-attributes)
>
> These two plugin will never change the file send in Github, because the edition happend during the page build. 

The plugin directly edit :
- [[Template/customization#Folder note|Folder note]]
- Categorization and custom tree creation

>[!warning] If you use your vault directly in a repo, the send will break your files! The script is not for theses strategies.

You can delete/disable safely the workflow named `ci.yml`, `manual_run.yml` and edit the `mkdocs_build.yml` to remove the `if:` line ([at the l18 lines](https://github.com/obsidianMkdocs/obsidian-mkdocs-publisher-template/blob/bff6d23ddf27064c39a2696159ad25e4a9554d3d/.github/workflows/mkdocs_build.yml#L18)).

## Python workflow

If you want to continue to rely on the python workflow, read bellow. 

> [!warning] About same repo & vault
> If you use your vault directly in a repo, the conversion by Obs2mk will break your files. The script is **not** for these strategies. 
> Example break:
> - Hashtags : `**2022/01**{: #2022/01 .hash}`
> - Callout converted to Admonition Mkdocs Callout
> - Your frontmatter
> - Links and internal path

> [!info] Configuration 
> The python script use the `minimal` configuration, and this configuration can be customized using a file named `configuration.yml` added in the root repo. 
> Here, you can disable the callout conversion and the hashtags conversion with:
> ```yaml
> minimal:
> 	convert:
> 		admonition: false
> 		hashtags: false
> ```
> Obviously, you can set one `true` and another `false`.
>> [!note]
>>If you disable the two, you don't need the obs2mk conversion (you will gain a LOT OF TIME for sharing). Just create a workflow on push for building mkdocs page.
>>To do that, just remove the `if` in the `.github/workflow/mkdocs_build.yml` file. 
