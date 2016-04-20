Originally written here with screenshots:
https://monsterbashseq.wordpress.com/2016/03/08/intro-git-lab-meeting/


By the end of this meeting, you will be able to:

* Create a new repository
* Edit readme.md (markdown lesson from Reid Brennan)
* clone to local desktop
* make changes
* commit and push changes

1. Create a new repository

From your github home directory: https://github.com/ljcohen/

Click on the "New" button to create a new repository:

    new_repository

Name the repository whatever you would like. Examples: test, data, lab protocols, awesome killifish RNA extractions, significant genes lists, abalone data files, etc. The idea is this will be your repository/directory with version-controlled files that you will pull/push back and forth between your computer and github. Click on the "Initialize this repository with README":

    create_repo

You have created a new repository!

    repo_created

2. Edit the README.md markdown file (Reid)

3. clone directory to local desktop

To copy the url, click on the clipboard-like icon next to the web address for this repository (see below). Sidenote: this is the same web address you can use to share this repository with colleagues. You can also just copy the url from the web address in your browser.

    clone

Open your terminal, navigate to a directory where you would like to put the new repository. Type this command to "clone" the repository:

git clone https://github.com/ljcohen/super_awesome_killifish_data.git
local_commandline.png

You should see the "Cloning into ___" like in the screenshot above. Use the 'ls' command to list the contents of the current working directory to make sure it's there. It is!

    ls

4. Make changes to the git directory

Now, we can make changes to this directory and they will be tracked. First, change directories into the one you just created:

cd super_awesome_killifish_data
Let's copy a file into this directory. (This is a small text file I had in one directory up from the current one, so I use ../ to indicate where it will be found then . to indicate that I want to copy it to the current directory.)

    cp ../cluster_sizes.txt .

5. Commit and push changes

Now that you have made a change to this directory, you want to make sure they are saved to github. The following commands are standard for staging and push changes to github repository:

    git status
    git add --all
    git commit -m "added cluster_sizes.txt for A_xenica"
    git push

(Type in your github user name and password. The letters you type in might not show up on the screen, but they are getting typed in, don't worry!)

    add_file

Now, you can go to the web github and see the changes made:

    changes_github.png

Useful References:

* https://swcarpentry.github.io/git-novice/
* http://dib-training.readthedocs.org/en/pub/2016-02-05-intro-git.html
* https://monsterbashseq.wordpress.com/2015/08/28/github-pull-requests-and-readthedocs-ngs2015/
* https://monsterbashseq.wordpress.com/2015/08/25/reproducible-research-using-rmarkdown-ngs2015-week-3/
