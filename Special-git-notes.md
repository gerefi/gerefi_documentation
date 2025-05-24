# Special Git Notes

One way to preview local changes to your fork of technical repository is to push those changes into your personal wiki git.

I only know how to do this from command line

```shell
git clone https://github.com/YOURNAME/gerefi_documentation.git
cd gerefi_documentation
git remote add personal-wiki-git https://github.com/YOURNAME/gerefi_documentation.wiki.git
git push --force personal-wiki-git master

```
