Data and Homework instructions
==============================

Stat 679: [Computing tools for data analytics](http://cecileane.github.io/computingtools),
Fall 2016

---

Data for homework assignments and group projects
are organized in different folders. See the readme file
in each folder for instructions on specific assignments.

1. follow these
[instructions](http://cecileane.github.io/computingtools/pages/git.html)
to install and configure git.
2. instructions to set up your homework repository with git,
  using one of 2 options: [github first](#option-1-github-first) or
  [work first](#option-2-start-your-work-first)
3. instructions to [submit](#commit-push-and-submit-your-work) your work
4. general grading [rubric](#grading-rubric)

---

## set-up your course repository

To submit homework and projects, use one repository, say `stat679work`,
that will contain several subdirectories: one per homework/project.
This repository should be *separate* from the `coursedata` repository.

In other words, you need to download the data for the course in a git repository
that is **kept separate** from your own directories when you do the work.
Git repositories **must not** be nested within one another.
(if you hear about submodules, forget about them for now).

Option 1 might be easier, but use
option 2 if you already started your work.

### option 1: github first

1. go to github and create a repository there, called "stat679work"
  for instance. Click on the "+" sign in the top right corner near your picture,
  then "New Repository". Click "Private" if you want to keep it private, which
  should be free through your student developer pack. Check the box to initialize
  the repository with a readme file called "README.md". Do *not* check the box
  if you would prefer to create this file yourself later, named "readme.md"
  for instance (that's my preference because lower-case letters save time).

2. still on github, in your new repo, click the green button "Clone or download",
  then click "Use SSH" on the right if you see "Clone with HTTPS" instead
  of "Clone with SSH". Copy the string (or click the "copy" button). The link
  should look like this:
  `git@github.com:your_user_name/stat679work.git`

3. on your laptop, nagivate to where you want your stat 679 work to be.
  This *must not* be inside an existing repository, so it must *not* be
  inside the directory with the stat 679 data. Then create your local
  version of your homework repository:
  `git clone git@github.com:your_user_name/stat679work.git`
  but paste the link that you copied in step 2.

4. move (`mv`) inside the new directory, which should be named with the name
  given in step 1 (like `stat679work`). Once there,
  * edit your readme file to explain what you intend to put in this directory
    and what subdirectories will be there,
  * create a subdirectory `hw1`
  * copy (`cp`) the data for homework 1 from `coursedata`
    to this new directory `hw1`.
  * create another readme file in `hw1` to explain what will be there,
    and how you got the data that is in there
    (copy-paste the command that was used in the previous step).

5. check that your local repository knows about the remote repository on github:
  `git remote -v`. You should see an output like this:

        origin	git@github.com:your_user_name/stat679work.git (fetch)
        origin	git@github.com:your_user_name/stat679work.git (push)

    if you do not get any output, then do step 7 in option 2 below.

6. save your work for homework 1 in `hw1`, organized with subdirectories
  to separate the data from your scripts. Instructions to "push" your work
  and to submit it are below.

### option 2: start your work first

3. create (`mkdir`) a directory `stat679work`, where you will do all of your work
  for the course, to be used to submit your homework and projects.
  This directory *must be* outside any other git repository, in particular,
  outside of the course data repository `coursedata`.

4. move (`mv`) inside your new directory `stat679work`. Once there,
  * create a `readme.md` file to explain what you intend to put in this directory
    and what subdirectories will be there,
  * create a subdirectory `hw1`
  * copy (`cp`) the data for homework 1 from `coursedata`
    to this new directory `hw1`.
  * create another readme file in `hw1` to explain what will be there,
    and how you got the data that is in there
    (copy-paste the command that was used in the previous step).

6. save your work for homework 1 in `hw1`, organized with subdirectories
  to separate the data from your scripts. Instructions to "push" your work
  and to submit it are below.

1. go to github and create a repository, called "stat679work" again.
  Click on the "+" sign in the top right corner near your picture,
  then "New Repository". Click "Private" if you want to keep it private, which
  should be free through your student developer pack. Do **not** check the box
  to initialize the repository with a readme file, because you already created
  a readme file in step 2.

2. still on github, in your new empty repository,
  copy the commands below "...or push an existing repository from the command line",
  which should look like this:

        git remote add origin git@github.com:your_user_name/stat679work.git
        git push -u origin master

7. move back to your `stat679work` directory (parent of `hw1`) to turn this
  directory into a git repository, then take your first "snapshot",
  with your readme file only to keep things simple. Once in `stat679work`,
  do this:

        git init                                     # initialize the repository
        git add readme.md                            # tell git to track the file readme.md
        git commit -m "initial commit: readme only"  # take the snapshot

    If you named your readme file differently (like readme or README or ReadMe or
  README.md or ReadMe.md), then adjust your `git add` command accordingly.
  Using the markdown style and having the extension `.md`
  is highly highly recommended.

5. tell your local repository about the remote repository on github: paste
  the commands copied in step 5, `git remote add ...` and then
  `git push -u origin master`. To check that git understood, do `git remote -v`.
  You should see an output like this:

        origin	git@github.com:your_user_name/stat679work.git (fetch)
        origin	git@github.com:your_user_name/stat679work.git (push)

## commit, push, and submit your work

These steps are to broadcast your work to github, to submit it there.

To do once:

- add your real name to your github profile, to make sure I know who you are!
  If you don't mind, please also add a picture of you.
- Share your repository, if you chose your repository to be private.
  Add "UWMadison-computingtools" as a collaborator to share it with the class,
  otherwise add me as collaborator at least.
  To share your repo with specific github users, click on
  "Settings" (near top right) then "Collaborator" (tab on the left), the
  search for a github user in the box "search by username ...". Once found,
  click "Add collaborator"

To do for each homework:

- save all your homework files locally
- commit the files that you want to submit
- run `git status` to double check
- push the new commit(s) to your github repo
- visit your repo on github, refresh the browser and make sure
  it's all good: click on the files, on the last commit,
  visit the network page (in "Graphs", then hover on the dots)

After these steps, your work will be visible (to all if public repo,
to collaborators if private).

To submit your work: open an issue, link to the latest commit, and tag me:

- find the SHA of the latest commit.
  On github, above the file list, look for "latest commit" followed by 7 numbers/letters.
  Right-click to copy the link to this last commit with its SHA. For example, it might
  look like this:
  `https://github.com/UWMadison-computingtools/coursedata/commit/0962e0575da1ead72884a8c6bc6c7910eb0169a3`
  You can also get the SHA from the shell: `git log`, but the first option gives the
  full link to that particular commit on the github repository.
- on github, click on "Issues", then "New Issue". Name your issue
  "Mark homework xxx, exercise yyy of firstname-lastname", where xxx and yyy are 1, 2, etc.
- issue description:
  * tag me by including the text @cecileane somewhere
  * paste the revision SHA (link from first step)
  * include comments to help me understand what you did
  * use Markdown syntax
  * click on "preview" to preview your issue (check the link)
- submit "new issue". I will receive an email automatically because you tagged me.

I will check your work online, will run your code to make sure it works,
then provide feedback on the "issue" if needed, and close the issue when
it's all done.

## get help on your work

You may also open an issue to get help. In this case, do as above but
choose a different name for your issue.

If I do not reply fast enough, I suggest that you share your repo with
the class (github user: "UWMadison-computingtools") and that you tag
someone else from the class, to get help from / discuss your issue with
someone else. Then use the github issue feature for your discussion.
Your goal is to learn these computing tools, so make sure you do the work
yourself, even if you ask for help from someone else.

## grading rubric

This general gradic rubric is vastly borrowed from Jenny Bryan's course's
[rubric](http://stat545.com/peer-review01_marking-rubric.html).
<!-- Stat 545 at University of British Columbia -->
For most assignments, the category for graph/table presentations will not apply.

| Topic | Excellent |	Satisfactory | Needs work |
|:------|:----------|:-------------|:-----------|
| code performance | efficient & lean code, using tools that are fast and that use memory efficiently, e.g. appropriate data structures | correct code, gets the work done with no error | some errors, job partially done, or in misplaced files |
| coding strategy | problem broken down into simpler sub-problems. Checks for common errors |	correct but lengthy code, e.g. from not using suitable data structures. Some checks for errors |	problem tackled in one big chunk, functions / subroutines not used to avoid code repetitiveness. No anticipation of errors.|
| coding style | human-readable code, good variable names, consistent indentation, coding manual, well commented functions and coding methods | readable code with comments, but style lacks refinement, may have some style errors |	many errors in coding style, little attention paid to making the code human readable |
| project documentation | each folder has its own `readme` file with a map of what is in the folder, how/when it got there, detailed notes & commands to reproduce the work, where to run each command, explanations of project goals and analysis choices. Markdown syntax is used, documentation well organized in sections & subsections | each folder had its own `readme` documentation, markdown syntax is used, most commands are there to reproduce the workflow, but it might not be clear in which order the commands / scripts need to be run, or from where, or what they each do. | missing project documentation, or present but difficult to follow and missing information |
Presentation: graphs & tables | graph(s) carefully tuned to convey a message | well chosen graph(s) but a few minor problems (e.g. aspect ratios, labels) | poorly chosen graphs, do not address questions |
| achievement, mastery, cleverness, creativity | beyond what was expected and required, e.g., extraordinary effort, additional tools not addressed by this course, unusually sophisticated application of tools from course |	tools and techniques from the course are applied very competently and, perhaps somewhat creatively. Chosen task was acceptable, but fairly conservative in ambition. | does not display the expected level of mastery of the tools and techniques in this course. Chosen task was too limited in scope. |
| work submission | access was made easy for instructor, the code runs | satisfactory access, complied with instructions | not an earnest effort to comply with conventions and/or code does not run |
