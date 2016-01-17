# Getting Started as a Connector Instructor

## Points of contact

**Sam Lau** (samlau95@gmail.com) and **Chris Holdgraf** (choldgraf@berkeley.edu)
are your current points of contact about issues and questions you may have
as a connector instructor. Email us with questions or [ping us in the chat room]
[gitter].

[gitter]: https://gitter.im/dsten/datascience

## Who is this for?

These guides are intended for connector instructors interested in creating
material that utilizes the same infrastructure as the main course.

Specifically, if you would like to use [**IPython notebooks**][ipython] and
optionally the [**`datascience`**][datascience] package in your course, this
guide is for you.

[ipython]: http://ipython.org/notebook.html
[datascience]: https://github.com/dsten/datascience

If you do not want to use this infrastructure that's fine by us. We'd be happy
to help you in whatever capacity we can.

## Setup

If you run into issues or questions with any of these steps, contact Sam or
Chris with your issue(s). It's our responsibility to make sure you have access
to the needed websites.

You'll need an account on https://data8.berkeley.edu/ . You should be able to
log in to that site with your @berkeley.edu email address. If you run into a:

![screenshot 2016-01-17 10 41 37](https://cloud.githubusercontent.com/assets/2468904/12379069/6dd0cf96-bd07-11e5-9261-18f99528f050.png)

This means that you don't have access yet. Ping either Sam or Chris.

You'll also need an account on [Github][github] and the ability to push to the
Github repo associated with your connector course.

[github]: https://github.com/

## Workflow

Here's a rough overview of the workflow we use in the main class. We'll base the
rest of this tutorial on these steps. Feel free to add/remove steps as fit for
your course.

Click a link to jump to that section of this guide.

1. [Create a notebook.](#creating-notebooks)
2. [Upload the notebook.](#uploading-your-notebooks)
3. [Distribute the notebook to students.](#distributing-notebooks)
4. [Students work on notebooks.](#student-work)
5. [Students submit their completed notebooks to you.](#student-submission)

[dsten]: https://github.com/dsten
[interact]: http://data8.org/text/1_data.html#example-plotting-the-classics

Let's talk in more detail about each of these steps.

### Creating notebooks

This guide is intended for those with no prior experience with Jupyter, `git`,
or Github. Feel free to develop your own workflow if you know what you're doing.

First, visit https://data8.berkeley.edu/ and log in. You should see a screen that
looks something like the one below. Click the "Terminal" button as marked:

![screenshot 2016-01-05 17 54 11](https://cloud.githubusercontent.com/assets/2468904/12132922/70ea3a22-b3d5-11e5-983a-6cd2aae3b10f.png)

You should see a screen that looks like this:

![screenshot 2016-01-05 17 56 14](https://cloud.githubusercontent.com/assets/2468904/12132944/a2dfd758-b3d5-11e5-920b-14b622d4efec.png)

This is a terminal that allows you to run commands. Type the following into the
terminal:

    git clone https://github.com/dsten/<repo_name>

Where the `<repo_name>` is the name of the repository for your connector. The
repository names are listed at https://github.com/dsten. For example, if you are
the instructor for the Health connector, you'd write:

    git clone https://github.com/dsten/health-connector

After this step, you should be able to see your connector's folder at
https://data8.berkeley.edu/ . Click on that folder to go inside that directory.

![screenshot 2016-01-05 18 02 28](https://cloud.githubusercontent.com/assets/2468904/12133071/a1a3be9e-b3d6-11e5-9efa-74cffcaba1e0.png)

You should see a screen like the one below. Click the button marked by the arrow
in the below image to create a new notebook. You may create a notebook in any
folder as long as the folder is in your connector folder. That is, in the
above example you may create a notebook in `~/health-connector/foo/bar/`, but
not `~/some_other_folder`.

![screenshot 2016-01-05 18 04 33](https://cloud.githubusercontent.com/assets/2468904/12133094/d7786e98-b3d6-11e5-8118-3a82bec33492.png)

Fill in the notebook with your content. For examples of notebooks, you can see
the [table demos][demos] or click any of the Interact buttons in [the
textbook][textbook]. The main class uses notebooks for lectures, labs, and
projects.

[demos]: https://github.com/deculler/TableDemos
[textbook]: http://data8.org/text/

### Uploading your notebooks

Once your notebook is ready for distribution, you must to upload it to Github so
that it can publicly accessed online.

For those who are familiar with `git` and Github, push your file to the
`gh-pages` of your repo. The file should then be available at
`http://data8.org/<repo_name>/<file_name>`.

If you are not familiar with `git`/Github, follow the instructions below.

1. On data8.berkeley.edu, open a new terminal. (New -> Terminal)
2. Type in

        cd <repo_name>

    Where the `<repo_name>` is the name of your repository (eg.
    `health-connector`).

3. Type

        git status

    You should see something that lists the files you've changed. If your
    changed files don't show up, ensure that they are in your repo's folder.

4. Type the following commands:

        git add -A
        git commit -m 'Update' # Feel free to make the message more descriptive
        git push origin gh-pages

5. Verify that you can access your file by visiting
`http://data8.org/<repo_name>/<file_name>`. For example, for the `Demo2.ipynb`
file in the `health-connector` repo you'd use the link:
http://data8.org/health-connector/Demo2.ipynb .

If the last step doesn't work, double the check the steps above and contact us
on a persisting issue.

### Distributing notebooks

Once your notebook is uploaded to Github, you can give your students links that
work like the Interact buttons in the textbook.

Create a link like the following:

    https://data8.berkeley.edu/hub/interact?repo=<repo_name>&path=<path_name>

Where the `<repo_name>` is replaced with your repo name and `<path_name>` is
replaced with the path to a file or folder in the repo.

For example, if you have a working link of
http://data8.org/health-connector/Demo2.ipynb, the link you'd give students is:

    https://data8.berkeley.edu/hub/interact?repo=health-connector&path=Demo2.ipynb

Any student that visits this link will end up with their own copy of the
`Demo2.ipynb` file in a folder called `health-connector` their
data8.berkeley.edu account. You can repeat this for any file, not just
notebooks.

Note that the first time a student does this it will be slow and may result in a
timeout in the browser. However, the student should eventually get the files.

Folders work too. If you have a folder called `datasets` in the
`health-connector` repo, you'd give students:

    https://data8.berkeley.edu/hub/interact?repo=health-connector&path=datasets

Updating works as well. If you update a file in the `datasets` folder, students
can grab the update by visiting the link again. Note that in some cases an
update would conflict with students' work (eg. updating a notebook that
students have filled out). In such a case, the system will give up trying to
update the file in favor of preserving the students' work.

### Student work

If you choose to use notebooks as assignments, students can then work on their
local copies of the notebook. For example, in the main class we have students
fill in notebook cells with their answers to questions.

### Student submission

Unforunately as of right now we don't have an easy way for students to submit
their work programmatically. You can accept submissions through email, bCourses,
or otherwise.

Students are currently able to download their notebooks off their
data8.berkeley.edu accounts in multiple formats, including `.pdf`, `.py`, and
`.ipynb`. They can download a notebook by opening it, turning Edit mode **on**,
then navigating to File -> Download as -> Format of choice.

Thus, feel free to collect student submissions in a format that makes sense for
you.
