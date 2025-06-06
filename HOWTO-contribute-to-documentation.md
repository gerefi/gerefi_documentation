# How to contribute to documentation

In order to leverage the Github pull request process for access control to the wiki, it is stored in a separate [Github repo](https://github.com/gerefi/gerefi_documentation).

## Editing

### Editing from a Wiki3 page

1. From the wiki page you wish to edit on [https://wiki.gerefi.com](https://wiki.gerefi.com), click on the "Edit on GitHub" link in the upper right hand corner.

2. Sign in to [Github](https://github.com) or sign up if you aren't already

3. Edit the page, scroll to bottom of page and enter a "change title" and clicking on "Propose Changes". This will fork the repository (if not created already), create a branch and give you the option to create a pull request.

   ![image](https://user-images.githubusercontent.com/22799428/200407238-74b1fd66-e6b1-46cc-a7b8-398f5c5b41f6.png)

4. Click "Create Pull Request" and wait for your change to be reviewed.

### Alternative: Editing from a fork of the repo

1. Sign up or sign in to [Github](https://github.com) if you aren't already

2. Open [the documentation repo](https://github.com/gerefi/gerefi_documentation) and click 'Fork' - this would produce your own fork/copy of gerefi_documentation which you can now edit right in your browser!
   ![editor](FAQ/github_online_editor.png)

3. Edit your code and Commit changes using the button below the editor.

4. Once you are ready to contribute your changes, click the 'New pull request' button on the main page of your fork.

### Alternative: Editing your fork locally

If you are using Linux, macOS, or WSL on Windows, this is a good option because it allows you to test your changes.

1. Fork the gerefi_documentation repo and clone it to your computer.

2. Make your changes.

3. [Test your changes](HOWTO-Test-Doc-Changes).

4. Push your changes to your fork on Github, and create a pull request.

### After creating a Pull Request

Within the next 5 minutes after the pull request has been merged, a Github Action automatically builds the wiki and uploads it to both wikis.

## How to contribute to gerEFI TunerStudio project

1. Sign up or sign in to [Github](https://github.com) if you aren't already

2. Go to  [https://github.com/gerefi/gerefi](https://github.com/gerefi/gerefi) and click "Fork" near the upper right corner

3. Edit your fork of [the TunerStudio input](https://github.com/gerefi/gerefi/blob/master/firmware/tunerstudio/gerefi.input) file

4. Click "Contribute", then "Open Pull Request", and finally "Create Pull Request"

5. Wait for your changes to be reviewed and merged.

[This commit](https://github.com/gerefi/gerefi/commit/9d9ae5a05499027b32ed76df3e7ee2e2e8240c31) is an example of how more help could be added
right into TunerStudio project file. Lines with green background are the lines being added.

Unfortunately while you would be modifying your mainController.ini file while trying your changes, you need to edit gerefi.input file which
is a template from which gerefi.ini is generated programmatically on gerefi side.

## Technical implementation details

Github Wiki is weird.

One the one hand, we have [https://github.com/gerefi/gerefi_documentation](https://github.com/gerefi/gerefi_documentation), which we will call "wiki-source".  
That's a git repository with nice pull request process, but less nice web page rendering which starts each page by showing a list of files - that's not what end users want to see.

On the other hand, we have [the Github Wiki](https://github.com/gerefi/gerefi/wiki), which we will call "wiki2" which is displayed much nicer - and that is actually implemented by ANOTHER git repository <https://github.com/gerefi/gerefi.wiki.git> behind the scenes.  
That repository does not have a nice Pull Request process :(

Solution? A combination. [wiki2](https://github.com/gerefi/gerefi/wiki) and [wiki-source](https://github.com/gerefi/gerefi_documentation) repositories are actually set to mirror each other.
This way we have the nice Pull Request process on [wiki-source](https://github.com/gerefi/gerefi_documentation) and once changes are merged, the wiki-source repo is then automatically merged into the wiki2 repo, which makes actual content nicely visible on [wiki2](https://github.com/gerefi/gerefi/wiki)  
Synchronization between wiki2 and wiki-source is automated via [Github Action](https://github.com/gerefi/gerefi/blob/master/.github/workflows/sync-wiki.yaml), file content is expected to be the same between these two repositories.

## How Page Titles Work on Wiki3

If the first line with content is a top-level header, e.g. `# gerEFI Documentation`, that will be used as the page title.
If not, the file name will be used as the page title, only without the hyphens.

## How URL links work in markdown documents

Links to page names use only the name of the page.
Example:

`[How to contribute to documentation](HOWTO-contribute-to-documentation)`  
Result:  
[How to contribute to documentation](HOWTO-contribute-to-documentation)

Links to images are relative to the root of the wiki on Wiki2, and relative to the .md file location on Wiki3.  
The only way for this to work consistently between Wiki2 and Wiki3 is to have a flat directory structure.
Example:

`![TunerStudio New Project View](FAQ/images/TunerStudio_new_project.png)`  
Result:  
![TunerStudio New Project View](FAQ/images/TunerStudio_new_project.png)

## Using URL link shortcuts

Link shortcuts are maintained in https://github.com/gerefi/web_backend/tree/master/www/s#readme

ToDo: explain rules when to use link shortcuts

## Technical FAQ

**Q:** Is there a place where we are holding all images for these documents?  
**A:** We have images in the same repository! Just add your images while editing pages. Please consider using some (any really) folder structure.
For example [https://github.com/gerefi/gerefi_documentation/blob/master/FAQ/images/TunerStudio_new_project.png](https://github.com/gerefi/gerefi_documentation/blob/master/FAQ/images/TunerStudio_new_project.png) is visible on wiki.gerefi.com as [https://wiki.gerefi.com/FAQ/images/TunerStudio_new_project.png](https://wiki.gerefi.com/FAQ/images/TunerStudio_new_project.png)

**Q:** What sort of fancy options do we have?  
**A:** We can do collapsible sections & hints sections! See [cranking](Cranking) for an example. Unfortunately, it's quite picky about how you format the markdown.

```html
<details markdown="1"><summary>More...</summary>

^ Must have empty line after </summary>
# Content
</details>

^ Must have empty line after </details>
```

**Q**: Is it ok that <https://github.com/gerefi/gerefi.wiki.git> cannot be opened from browser?  
**A**: There is no reason to open <https://github.com/gerefi/gerefi.wiki.git> from browser. Also while you technically
CAN "git clone <https://github.com/gerefi/gerefi_documentation.wiki.git>" and it would work -
 you should NOT. Anyone looking to make changes should be making changes to non-wiki git via normal fork & pull request process.

Additional automation is in charge of merging from <https://github.com/gerefi/gerefi_documentation.git> into <https://github.com/gerefi/gerefi_documentation.wiki.git>
