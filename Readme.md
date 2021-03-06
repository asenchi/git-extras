
# Git Extras

 Little git extras.

## Installation

     $ make install

## Commands

 - git summary
 - git changelog
 - git commits-since
 - git count
 - git delete-branch
 - git delete-tag
 - git ignore
 - git release
 - git contrib
 - git repl

## git-contrib

Output a user's contributions to a project, based on the author name:

    $ git contrib visionmedia
    visionmedia (18):
      Export STATUS_CODES
      Replaced several Array.prototype.slice.call() calls with Array.prototype.unshift.call()
      Moved help msg to node-repl
      Added multiple arg support for sys.puts(), print(), etc.
      Fix stack output on socket error
      ...

## git-summary

Outputs a repo summary:

  $ git summary

	  project: express       
	  commits: 1893          
	  files  : 111           
	  authors:               
	   1285	visionmedia    
	    478	Tj Holowaychuk 
	     48	Aaron Heckmann 
	     34	csausdev       
	     26	ciaranj        
	      6	Guillermo Rauch
	      3	Nick Poulden   
	      2	Brian McKinney 
	      2	Benny Wong     
	      1	Justin Lilly   
	      1	James Herdman  
	      1	Adam Sanderson 
	      1	Viktor Kelemen 
	      1	Gregory Ritter 
	      1	Greg Ritter    
	      1	ewoudj         
	      1	isaacs         
	      1	Matt Colyer    


## git-repl

 GIT read-eval-print-loop:

     $ git repl
     
     git> ls-files
     History.md
     Makefile
     Readme.md
     bin/git-changelog
     bin/git-count
     bin/git-delete-branch
     bin/git-delete-tag
     bin/git-ignore
     bin/git-release
     
     git> quit

## git-commits-since [date]

 List of commits since the given _date_, defaulting to "last week":

    $ git commits-since
    ... changes since last week
    TJ Holowaychuk - Fixed readme
    TJ Holowaychuk - Added git-repl
    TJ Holowaychuk - Added git-delete-tag
    TJ Holowaychuk - Added git-delete-branch

    $ git commits-since yesterday
    ... changes since yesterday
    TJ Holowaychuk - Fixed readme

## git-count

 Output commit total:

    $ git count

    total 1844

 Output verbose commit count details:

    $ git count --all

	visionmedia (1285)
	Tj Holowaychuk (430)
	Aaron Heckmann (48)
	csausdev (34)
	ciaranj (26)
	Guillermo Rauch (6)
	Brian McKinney (2)
	Nick Poulden (2)
	Benny Wong (2)
	Justin Lilly (1)
	isaacs (1)
	Adam Sanderson (1)
	Viktor Kelemen (1)
	Gregory Ritter (1)
	Greg Ritter (1)
	ewoudj (1)
	James Herdman (1)
	Matt Colyer (1)

	total 1844

## git-release

 Release commit with the given &lt;tag&gt;.
	
	$ git release 0.1.0
 
 Does the following:

   - Commits changes (to changelog etc) with message "Release &lt;tag&gt;"
   - Tags with the given &lt;tag&gt;
   - Pushes the branch / tags

## git-ignore

 To lazy to open up _.gitignore_? me too! simply pass some patterns:

    $ git ignore build "*.o" "*.log"
	... added 'build'
	... added '*.o'
	... added '*.log'

## git delete-branch &lt;name&gt;

 Deletes local and remote branch _name_.

    $ git delete-branch integration

## git delete-tag &lt;name&gt;

 Deletes local and remote tag _name_.

    $ git delete-tag 0.0.1

## git-changelog

  Populates the file named matching _change|history -i_ with the commits
since the previous tag or since the project began when no tags are present. Opens the changelog in **$EDITOR** when set.

    $ git changelog && cat History.md
    
    n.n.n / 2010-08-05 
    ==================
    
    * Docs for git-ignore. Closes #3
    * Merge branch 'ignore'
    * Added git-ignore
    * Fixed <tag> in docs
    * Install docs
    * Merge branch 'release'
    * Added git-release
    * Passing args to git shortlog
    * Added --all support to git-count
    * Initial commit
    
Listing commits:
    
    $ git changelog --list

    * Docs for git-ignore. Closes #3
    * Merge branch 'ignore'
    * Added git-ignore
    * Fixed <tag> in docs
    * Install docs
    * Merge branch 'release'
    * Added git-release
    * Passing args to git shortlog
    * Added --all support to git-count
    * Initial commit
