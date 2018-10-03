# fellows-guide

## Structure

Each side-bar item is one .md file in the `docs` folder. To create the sub-sections under each item, you would need to create a new heading. For example:

```
# Sidebar item name (Heading 1)

## Sidebar sub-section name (Heading 2)

### Sidebar sub-section item (Heading 2.1) - does not appear a sub-section

```

Only the first two headings type will appear as a section/sub-section. If your first heading starts with a `#` tag, that will be the section name. If your second heading starts with `##`, that will create a sub-section under the parent item in the sidebar. 

Any following `##` tags will also be sub-sections under that item. Any tags that follow with a `###` or `####` will not be included as sub-sections in the sidebar.

## Updating this Guide

The guide is served on the gh-pages branch of this repo and written in Markdown.

### Installation

#### Installing pip

If you're using a recent version of Python, the Python package manager, pip, is most likely installed by default. However, you may need to upgrade pip to the lasted version:

``` pip install --upgrade pip ```

If you need to install pip for the first time, download get-pip.py. Then run the following command to install it:

```python get-pip.py```

#### Installing MkDocs

Install the `mkdocs` package using pip:

```pip install mkdocs```

You should now have the mkdocs command installed on your system. Run `mkdocs --version` to check that everything worked okay.

** **Note** **: If you are using Windows, some of the above commands may not work out-of-the-box.

A quick solution may be to preface every Python command with python -m like this:

```
python -m pip install mkdocs
python -m mkdocs
```

### Making local changes and deployment

Once you have install `mkdocs` follow these steps.

**Team Members**: To update this guide (team members only), follow the steps below:

- Clone the project using `git clone https://github.com/MicrosoftTCE/fellows-guide.git`
- Change directory to the project folder by running `cd fellows-guide`
- Make your local changes and view them locally by running `mkdocs serve` and navigating to `http://127.0.0.1:8000/` in your browser
- Build your files to get ready for deployment by running `mkdocs build`
- Run `git status` to check which files have been updated
- Add your changes individually by file `git add <file-name>` or add all files at once by running `git add .`
- Commit your changes by running `git commit -m "your_comment"`
- Deploy your changes by running `mkdocs gh-deploy`

Your changes will be deployed to the gh-pages branch of the repo and will be updated at <https://microsofttce.github.io/fellows-guide/>


**Outside Contributors:** If you are an outside contributor, follow these steps:

- Fork the project and clone it on your local computer
- Change directory to the project folder by running `cd fellows-guide`
- Run `git pull` to pull in any remote changes
- Make your local changes and view them locally by running `mkdocs serve` and navigating to `http://127.0.0.1:8000/` in your browser
- Build your files to get ready for deployment by running `mkdocs build`
- Run `git status` to check which files have been updated
- Add your changes individually by file `git add <file-name>` or add all files at once by running `git add .`
- Run `git pull` again in case any changes were made recently and fix any merge conflicts
- Commit your changes by running `git commit -m "your_comment"`
- Deploy your changes by running `mkdocs gh-deploy`
- Create a pull request from your forked repo on Github.com. The pull request should go from your gh-pages branch into the master repo  **base fork: MicrosoftTCE/fellows-guide, base: gh-pages**

Once the pull request has been approved, your changes will be merged into the main repo.

---

### Adding content

This guide is written in Markdown. A cheatsheet for Markdown commands is available here: <https://www.markdownguide.org/cheat-sheet>

Basic Markdown syntax is also here: <https://www.markdownguide.org/basic-syntax>

To add a new page to this guide, create a new `.md` file and add it to the `docs` folder in this project. 

To add the new page to the nav sidebar, open the `mkdocs.yml` file and add a new item under `pages` in the file. The words before the colon is the title of the page as it will appear in the guide and after the colon is the name of the `.md` file.

Run the project locally using  `mkdocs serve` to confirm your new content is available.
