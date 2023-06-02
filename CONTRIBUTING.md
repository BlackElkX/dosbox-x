## Setting up the dev environment (extremely brief version)

This is a [Jekyll](https://jekyllrb.com/) site. If you want to develop it, I recommend to install the site's dependencies with [Bundler](https://bundler.io) assuming that you have Ruby installed:
```sh
$ bundle install
```

Then you can utilize the Jekyll CLI to preview your changes to the site locally and live:
```
$ bundle exec jekyll serve
```

## Updating the latest version

Before doing this, you probably want to make sure all files for the release are ready and uploaded to GitHub, to make users' life easier

1. Add a release notes page for the latest version - see [adding a release note page](#adding-a-release-note-page)
2. Open [`_data/latest_version.yml`](_data/latest_version.yml)
3. Edit the fields accordingly
4. You're basically done

## Adding a release note page

1. Create a file in [`_release_notes/`](_release_notes/) by the name of `<release name>.md` and open it
2. Add a front matter like below to the start of the file, then append a new line after it
    ```markdown
    ---
    date: "<insert release date of version>"
    ---
    ```
3. Extract the release notes from `CHANGELOG` or write your own, make sure it's in Markdown format, then append it to the file
4. Optionally, serve the site and tinker until the page looks OK
5. You're basically done

## Updating the wiki

> If you mean to contribute to the wiki, I'll direct you to [rderooy/dosbox-x-wiki](https://github.com/rderooy/dosbox-x-wiki) as that's where wiki updates are pulled from right now

First if you haven't yet, clone https://github.com/joncampbell123/dosbox-x.wiki.git outside this repo first, and install site dependencies.

After you have those stuff ready, you can now do something like this in Bash to update the wiki:
```bash
$ cd path/to/dosbox-x.wiki.git
$ git pull

$ cd path/to/dosbox-x-gh-pages
$ ./update-wiki ./wiki path/to/dosbox-x.wiki.git
```