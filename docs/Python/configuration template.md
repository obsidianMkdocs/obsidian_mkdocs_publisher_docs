---
share: true
---
```yaml
default: #change the name if you need a new configuration setting  
  configuration:  
    input: #your obsidian vault in absolute path
    output: #Your mkdocs site in absolute path
  frontmatter:  #change these if you need
    category:  
      default value: #default folder/category if no category key is present
      key: #category  
    index: #(i)  
    share: #share  
  convert:
	admonition: #true or false
	hashtags: #true or false
  weblink: #links to your website
```


If you need a new configuration, just copy/paste after the other configuration, without forgetting to change the `default` to your `configuration_name`

Some explanation here. It's a [YAML](https://en.wikipedia.org/wiki/YAML) file. If you use the script in terminal you **need** to configure it. No worry! Normally, the script ask you all information. 

> [!Note] If you need to edit it, the file is in your `site-packages/mkdocs_obsidian`. 
>  You can check this place with:
> ```python
>  import mkdocs_obsidian as obs
>  print(obs.__path__[0])
>  ```

Thus :
- `input` : corresponding to your vault, in an absolute path.
- `output` : your mkdocs repository folder, in an absolute path. 
- `frontmatter` : 
	- `category` : 
		- `default value` : The default folder for new notes that don't have this key in the front matter.
		- `key` : If you want to change the category key for other things. For example, `folder`.
	- `index` : for [[Python/customization#Folder note|folder note]], citation will be broken, but this key prevents problem! Note, set this to null or empty will disallow the index link conversion. 
	- `share` : if you wish to use another key to authorize the file to be shared.
- `convert` : Allow the script to convert some QoL, as hashtags and admonition
	- `admonition`: `True` for allow the convertion of callout
	- `hashtags` : `True` for [[Template/customization#Tags|tags]]


> [!info] Update for minimal configuration
> As of the update to v4.0.2, the script doesn't need minimal configuration for running with GitHub actions.  You can safely deleting it.

> [!info] 4.1 new options
> The 4.1 version adding a way to disable callout conversion and hashtags. To disable them, you need to add a new part in your workflow:
> ```yaml
> configuration_name:
> 	#old configuration part
> 	convert:
> 		admonition: false
> 		hashtags: false
> ```
> This work also for minimal configuration. For this, you need the `configuration.yml` in the root of your repository, with :
> ```yaml
> minimal:
> 	convert:
> 		admonition: false
> 		hashtags: false
> ```
