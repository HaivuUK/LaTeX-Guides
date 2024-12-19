# Collaboration

In LaTeX collaboration is not normally at the forefront of the workflow. However, it is possible to do in a few ways.
The main options are a Version Control System (VCS) like Git, a cloud-based LaTeX editor like Overleaf, or a
more general collaboration plugin for an editor like Atom or Visual Studio Code.

!!! Note
    More than basic collaboration in Overleaf is a paid for feature.

## Version Control Systems

Version Control Systems (VCS) are a way to track changes to files over time. They are commonly used in software 
development to track changes to code, but can also be used for LaTeX documents (which are essentially code). 
The most popular VCS is Git, which is free and open source. Git is a distributed VCS, which means that each user
has a full copy of the repository on their local machine. This makes it easy to work offline and to collaborate
with others. However, you can also use a centralised Git repository, like GitHub, GitLab, or Bitbucket, to collaborate
with others.

It is recommended to keep separate branches when working on a LaTeX document with others. This way, you can work on
different parts of the document without interfering with each other. When you are ready to merge your changes, you can
create a pull request, which allows others to review your changes before they are merged into the main branch.

Git integrates well with nearly all LaTeX editors such as TeXstudio and Visual Studio Code. You can also use Git from
the command line or a GUI client like Sourcetree or GitHub Desktop.

Additionally, if you are using a tool like GitHub you can use GitHub Actions to automatically compile your LaTeX 
document on a trigger you define, such as a push to the repository. This can be useful for a collaborative project
where not everyone has LaTeX installed on their machine. 
[GitHub Action To Compile LaTeX](https://github.com/marketplace/actions/compile-latex).

For more information to get started with Git, see the following resources:

- [official documentation](https://git-scm.com/doc)
- [GitHub's Git Handbook](https://guides.github.com/introduction/git-handbook/) 
- [Pro Git book](https://git-scm.com/book/en/v2)
- [Learning Git Branching](https://learngitbranching.js.org/)
- [Visual Guide to Version Control](https://betterexplained.com/articles/a-visual-guide-to-version-control/)

## Visual Studio Code Live Share

This is a plugin for Visual Studio Code that allows you to collaborate with others in real-time. It is free and open
source, and works with any programming language, including LaTeX. It has features like real-time editing, debugging,
and text chat. This arguably provide the best real-time collaboration experience for LaTeX documents as it in most
cases does not require any specific changes to pre-existing workflows.

[Visual Studio Code Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)

[Live Share Info](https://visualstudio.microsoft.com/services/live-share/)

The main downside to this is that it requires a session to be started and maintained, which could be a problem if you
want to work on the document offline or flexibly. It is always best to use a tool like Git in conjunction with this.

## Overleaf

!!! Note
    Overleaf limits collaboration features on free accounts to one collaborator and no real-time track changes.

Overleaf provides a combination of real-time collaboration and version control in a single paid service.

Overleaf allows you to collaborate with others in real-time. It has a built-in version control system, so you can see 
who made changes to the document and when in addition to leaving comments.
Overleaf integrates reasonably well with Git if you want a further backup of your document but has some known
limitations such as not being able to branch.

For more information on Overleaf, see the following resources:

- [official documentation](https://www.overleaf.com/learn)
- [Overleaf's Git integration](https://www.overleaf.com/learn/how-to/Git_integration)

