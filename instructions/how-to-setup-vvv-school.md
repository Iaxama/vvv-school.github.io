# How to set up a VVV{YY} School

**YY** is the school year (e.g. **17**, **18**...)

## Introduction

### Basic concepts

1. The repository [**vvv-school/vvv{yy}**](#set-up-vvvyy-school-repository) represents the "hall" of the school, that is the school entry point. It's where we handle the Wiki, the Q&A system, school material (e.g. links to slides) and, generally, all the resources we need. With [GitHub Pages](https://pages.github.com) we can render the hall quite nicely.
1. Each day we'll run a **course** (e.g. kinematics, dynamics, vision...) that consists in teaching theories during **frontal lessons** so as giving [**hands-on**](#hands-on) sessions.
1. Teachers have two instruments during hands-on and/or lessons: [**tutorials**](#tutorials) and [**assignments**](#assignments). They correspond to single repositories stored in [**vvv-school** organization](https://github.com/vvv-school).
1. Teachers make use of [GitHub Education](https://education.github.com) to invite students to follow tutorials and solve assignments. To this end, each teacher is required to set up a new organization where students' assignments will be created by means of _automatic sandboxing_ through [**GitHub Classrooms**](https://classroom.github.com).
1. Provided that there are many attendees, we cannot afford to do [**code review**](../instructions/how-to-complete-assignments.md#collaborative-code-review-1) on a student basis. Alternatively, we can resort to [**automatic grading**](#automatic-grading) to challenge students and let teachers understand which of them falls behind, thus needing help.
1. Material specific to _VVV{YY} School_ can be conveniently put inside **vvv{yy}** repository. Instead, for collecting **courses material** that can be _recycled yearly_, we can either rely on **individual repositories** hosted at [**vvv-school** organization](https://github.com/vvv-school) (call it **material_**_something_), or on external resources we can link to. Please, don't use [vvv-school.github.io](https://github.com/vvv-school/vvv-school.github.io) for such kind of storage, since slides can be easily very unwieldy. Remarkably, teachers may consider resorting to [**GitPitch**](https://gitpitch.com) to publish their presentations in markdown as repositories.

## Set up VVV{YY} School repository

The repository will be named **vvv-school/vvv{yy}** (e.g. [vvv-school/vvv17](https://github.com/vvv-school/vvv17)).

Everything is already mostly done, since we can [**import** the repository](https://help.github.com/articles/importing-a-repository-with-github-importer) **vvv{yy-1}** into **vvv{yy}**. Note that **importing** seems a better choice than **forking**: we break up any _subtle relationship_ between the two repositories.

Then, do the following steps:
- If you didn't do it while creating the new repository, edit the **description** and the **website** fields of the repository page with, respectively, **Resources for VVV{YY} School** and **https://vvv-school.github.io/vvv{yy}**.
- Within [vvv-school](https://github/vvv-school), [create two **teams**](https://help.github.com/articles/creating-a-team): **vvv{yy}-teachers** and **vvv{yy}-students**. Start off filling in the teachers team for the time being, while we will be waiting for all students to sign up on GitHub. Remember that teams visibility is restricted to the organization's members, hence don't spread out links that non-members won't be able to access. In particular, **vvv{yy}-students** will be used during [**automatic grading**](#automatic-grading).
- Add up **vvv{yy}-students** as [**team with read permission**](https://help.github.com/articles/managing-team-access-to-an-organization-repository) to **vvv{yy}**, so that students can edit the Wiki.
- Replace all the links in **README.md**, **teachers.md** and **students.md** files accordingly.
- Create a [**welcome issue**](https://github.com/vvv-school/vvv17/issues/1) in **Q&A**. Don't forget to replace links therein too.
- Replicate the same **Wiki** of **vvv{yy-1}** repository; it's quite slim and it shouldn't require a big effort :wink: In particular, you need to fill in the home page and create one further page containing the [**instructions to follow before arriving at VVV**](https://github.com/vvv-school/vvv17/wiki/Before-arriving-at-VVV) (link this page from home).
- [Configure the **GitHub Pages**](https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/#enabling-github-pages-to-publish-your-site-from-master-or-gh-pages) to publish from the **`master`** branch. The file **`_config.yml`** used by GitHub Pages to set up the style should be already contained inside (thanks to duplication). This way, the website of the resources of VVV{YY} School will be published at https://vvv-school.github.io/vvv{yy} (e.g. https://vvv-school.github.io/vvv17).
- Fill in the file **gradebook.md** with proper links to the GitHub page of the [courses repositories](#vvvyy-school-courses-repositories).

## Set up VVV{YY} School courses organizations

During **vvv{yy}** school, teachers will be giving **frontal lessons** and **hands-on sessions** regarding diverse courses, e.g. **kinematics**, **dynamics**, **vision** and so on.

### Hands-on
**Hands-on** are repositories stored in [**vvv-school** organization](https://github.com/vvv-school), which we handle using the [**GitHub Education**](https://education.github.com) platform.

There are two categories of hands-on:

#### Tutorials
>A tutorial is a repository containing complete code used to explain a particular aspect of the course. During lessons and/or hands-on, teachers and students can work on it together. Tutorials will be therefore assigned within the classroom, even though students are not required to provide any solution (the code is complete); thus, their score is low (e.g. **1,2**). A tutorial may or may not provide a [**smoke-test**](https://github.com/vvv-school/vvv-school.github.io/blob/master/instructions/how-to-complete-assignments.md#smoke-testing); at any rate, it won't be counted by [**automatic grading**](#automatic-grading) process.

>[**tutorial_cartesian-interface**](https://github.com/vvv-school/tutorial_cartesian-interface) is an example of tutorial you can design yours from.

>Be tidy and call your tutorials with the prefix **tutorial_**.

#### Assignments
>An assignment is a repository that contains **starter code** the students are required to complete with their own solutions. To run the [**automatic grading**](#automatic-grading) process based on assignments, teachers responsible for the course need to code a [**smoke-test**](https://github.com/vvv-school/vvv-school.github.io/blob/master/instructions/how-to-complete-assignments.md#smoke-testing) inside the assignment. Typically, assignments have higher scores (e.g. **> 2**) depending on their difficulty.

>Students can follow these [general **instructions**](../instructions/how-to-complete-assignments.md#instructions-for-students) to complete the assignments; in particular, the section on [**Smoke Testing**](../instructions/how-to-complete-assignments.md#smoke-testing) that will help check whether the assignment can be considered passed. Also, an assignment contains **specific instructions** (within _README.md_) detailing how students should proceed with the code. Note that nothing prevents a teacher from accepting an assignment himself and solve it together with students. Teachers are suggested to store a possible solution to the assignment as a **private repository** within [**vvv-school** organization](https://github.com/vvv-school) (let's call it **solution_**_name-of-assignment_). Once the course is over, we can decide to **disclose** solutions by simply adding up **vvv{yy}-students** as [**team with read permission**](https://help.github.com/articles/managing-team-access-to-an-organization-repository).

>[**assignment_make-it-roll**](https://github.com/vvv-school/assignment_make-it-roll) is an example of assignment you can design yours from.

>Be tidy and call your assignments with the prefix **assignment_**.


Thereby, to deal with students hands-on for each course, we have to create the dedicated organization **vvv{yy}-{course}**. This choice allows us to use a [**GitHub Classroom**](https://classroom.github.com) specific to each course as well as to avoid cluttering the main [**vvv-school** organization](https://github.com/vvv-school) with lots of students repositories that will be automatically generated by means of the classroom process.

Therefore, for each course, do:
- [Create the **organization**](https://help.github.com/articles/creating-a-new-organization-from-scratch) **vvv{yy}-course**.
- It's not strictly necessary to give all teachers read/write permissions to the organization: one maintainer per course is enough :wink:
- [Create a brand new **classroom**](https://classroom.github.com/classrooms/new) on top of **vvv{yy}-{course}**. You should see **vvv{yy}-{course}** within the list of available organizations; if not, grant GitHub access first (click on the link at the bottom of the page).


### VVV{YY} School courses repositories

Each course is managed through a **course repository**, which is thus named **vvv{yy}-{course}/vvv{yy}-{course}.github.io** and aims to automatically handle the **course gradebook**.

Then, let's create this last repository! Also here, everything is already mostly done: you can [**import** the template repository](https://help.github.com/articles/importing-a-repository-with-github-importer) [**vvv-school/template_vvvyy-course.github.io**](https://github.com/vvv-school/template_vvvyy-course.github.io) into **vvv{yy}-{course}/vvv{yy}-{course}.github.io**.

To start with, you need to apply the following changes:

- Edit the **description** and the **website** fields of the repository page.
- **GitHub Pages** are already enabled by default, given the chosen name of the repository. The file **`_config.yml`** used by GitHub Pages to set up the style should be already contained inside (thanks to duplication).
- Edit the first line of [**README.md**](https://github.com/vvv-school/template_vvvyy-course.github.io/blob/master/README.md) file. The rest of the file will be overwritten by the [**automatic grading**](#automatic-grading) process.
- Edit the _organization's name_ so as the the _students' team name_ within the [**gadebook.sh**](https://github.com/vvv-school/template_vvvyy-course.github.io/blob/master/gradebook.sh#L11-L12) script.
- **Pin the repository** to the organization.
- Remember to put a link to _https://vvv{yy}-{course}.github.io_ inside **vvv-school/vvv{yy}/gradebook.md**.

#### Gear up for automatic grading

Finally, you have to fill in the **data.json** file containing info on **tutorials** and **assignments** regarding this particular **{course}**.

The format is pretty much intuitive. Here's an example:
```json
{
    "tutorials": [
        {
            "name": "tutorial_gaze-interface",
            "url": "https://github.com/vvv-school/tutorial_gaze-interface.git",
            "score": 1
        },
        {
            "name": "tutorial_cartesian-interface",
            "url": "https://github.com/vvv-school/tutorial_cartesian-interface.git",
            "score": 1
        }      
    ],
    
    "assignments": [
        {
            "name": "assignment_make-it-roll",
            "url": "https://github.com/vvv-school/assignment_make-it-roll.git",
            "score": 5
        }    
    ]    
}
```
Be careful, a repository can be **listed only once**.

## Automatic grading

**Automatic grading** is a process that runs continuously in background to collect information from students submissions to then publish results nicely.

We have to go through two steps:

### Challenge students

Once you're all set, you can [create an **individual assignment**](https://education.github.community/t/video-setting-up-individual-assignments/2150) from the dashboard of your **GitHub Classrom**.

These are the settings we have to use:
- **Your assignment title**: make up a name; it's not that significant.
- **Your assignment repository prefix**: :warning: must be equal to the name of the **starter code** (e.g. _assignment_make-it-roll_) :warning:
- Tick on **Public** :white_check_mark:
- **Don't give students** _Admin permissions_ on their repository :x:
- **Add your starter code from GitHub**: pick up your tutorial or assignment from [**vvv-school**](https://github.com/vvv-school). **Autocompletion** is available to help you out :octocat:

You'll be given an **invitation link** you must now share with students. The easiest and the most collaborative way is to post it on the **Q&A** system: https://github.com/vvv-school/vvv{yy}/issues.

Repeat the process for all the hands-on you have in your course. It can be done all at once, or progressively, depending on the pace that suits you best.

At this point, students can follow these [general **instructions**](../instructions/how-to-complete-assignments.md#instructions-for-students) to complete the assignments; in particular, the section on [**Smoke Testing**](../instructions/how-to-complete-assignments.md#smoke-testing).

In case you, the teacher, decide to solve an assignment together with students, proceed as follows:
- **click on the invitation link** to accept the assignment yourself;
- during the hands-on, work within the newly created repository alongside with students;
- highlight the use of **smoke-test**;
- your contribution won't be put on the bill during automatic grading, since you're not a member of **vvv{yy}-students** team.

### Update the gradebook

We use a **Linux system** to run the script for the automatic grading.

#### Prerequisites 

- you have to [store **git credentials**](https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage) locally, to let git push without keep prompting for login.

  >To store credentials for one hour:
  ```sh
  $ git config [options] credential.helper 'cache --timeout=3600'
  ```
  To flush the cache earlier:
  ```sh
  $ git credential-cache exit
  ```
  To store credentials forever (or until you erase):
  ```sh
  $ git config [options] credential.helper store
  ```
  To unset storing credentials:
  ```sh
  $ git config [options] --unset-all credential.helper
  ```
  `options` can be:
    >- `--local` affecting only the current git directory.
    >- `--global` affecting all git directories of the current user.
    >- `--system` affecting all git directories on the system.

- Additionally, you have to be a **OAuth user** with `read:org` scope to retrieve from [GitHub API](https://developer.github.com/v3/orgs/teams/) reserved information regarding teams. To do so, after you created a [personal access token on GitHub](https://help.github.com/articles/creating-an-access-token-for-command-line-use), save the token in the environment variable **GITHUB_TOKEN_ORG_READ**:
  
  ```sh
  $ export GITHUB_TOKEN_ORG_READ=token-hash-goes-here
  ```
  
  If you don't want to mess up with your user account credentials, you might consider being the [**vvv-school-bot**](https://github.com/vvv-school-bot) instead :wink: (ask [**@pattacini**](https://github.com/pattacini) to get the password). To this aim, invite [**vvv-school-bot**](https://github.com/vvv-school-bot) to be a collaborator of **vvv{yy}-{course}/vvv{yy}-{course}.github.io** with _write permission_.
- Make sure that [**curl**](https://curl.haxx.se) and [**jq**](https://stedolan.github.io/jq) are installed. We use the latter to parse [GitHub API](https://developer.github.com/v3) responses.

  ```sh
  $ sudo apt install curl
  $ sudo apt install jq
  ```

#### Launch the script

```sh
$ git clone https://github.com/vvv{yy}-{course}.git
$ cd vvv{yy}-{course}
$ ./gradebook.sh
```

The gradebook will be published online at the course webpage: _https://vvv{yy}-{course}.github.io_.
