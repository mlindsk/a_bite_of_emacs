
# Table of Contents

1.  [Emacs](#org5ab93d0)
2.  [How To Use Emacs](#orgd978043)
3.  [The Basics](#org996d11e)
    1.  [Buffers and Mini buffers](#orge475727)
    2.  [Windows and Frames](#orgc679717)
    3.  [Keybindings](#org464faed)
        1.  [Nomenclature](#org3ef4e3b)
    4.  [Some Important Ones](#orgd1016c8)
        1.  [Killing and Yanking](#org150f7fe)
        2.  [Rectangles](#org8c051da)
    5.  [Modes](#orgf725bf1)
        1.  [Major Modes](#org14a34f4)
        2.  [Minor Modes](#orgcf0fb7f)
4.  [Multiple Cursors](#org8e37469)
5.  [Dired Mode](#orgcc65e5d)
6.  [Bookmarks](#orgf0e57a4)
7.  [The init.el File](#org63779e1)
    1.  [Melpa](#org6070b1e)
8.  [AucTex](#org400e4e3)
9.  [Emacs Speaks Statistics](#orgb16d3b3)
    1.  [R](#orga43d9eb)
        1.  [Debugging](#org2005f46)
        2.  [Package mode](#org8b20d9d)
        3.  [Controlling buffer display](#orgdddca1a)
10. [Polymode](#org8b39af7)



<a id="org5ab93d0"></a>

# Emacs

[Emacs Logo](img/emacs.png)

-   Text editor (on steroids)

-   Initial release in 1976 (43 years ago!)
    -   Richard Stallman began the GNU Emacs in 1984 (free version)

-   Stable release 26.2

-   Cross-platform

-   Active community

-   Extensible and customizable


<a id="orgd978043"></a>

# How To Use Emacs

1.  Learn the basics and be happy.

2.  Learn some advanced commands that suit your needs.

3.  Constantly look for new commands to speed up editing.

4.  Progress to write your own totally new Emacs commands.


<a id="org996d11e"></a>

# The Basics


<a id="orge475727"></a>

## Buffers and Mini buffers

-   A **buffer** is an interface between Emacs and a file or process.
    -   Equivalent to tabs/panes (and its content).

-   The **minibuffer** is a special buffer.
    -   Often a window occupying a single line.


<a id="orgc679717"></a>

## Windows and Frames

-   A **window** is a view onto a buffer.
    -   Two windows are what you would split screen in other contexts.

-   A **frame** is the \`container\`.
    -   Called a window in most other contexts.

[Working with windows and frames - video](https://www.youtube.com/watch?v=aIMECr7K35Q)


<a id="org464faed"></a>

## Keybindings


<a id="org3ef4e3b"></a>

### Nomenclature

-   `C-<key>`            : Press control and <key>

-   `C-<key1> C-<key2>`  : Press control and <key1> release and 
    press control and <key2>

-   `M-x` (M = Meta key) : Alt-x -> type a command; e.g. list-packages


<a id="orgd1016c8"></a>

## Some Important Ones

1.  `C-g`        : undo the current command
2.  `C-x b`      : switch to other buffer
3.  `M-<`        : go to beggining of buffer
4.  `M->`        : go to end of buffer
5.  `C-s`        : incremental search
6.  `C-r`        : search backward
7.  `C-e`        : end of line
8.  `C-a`        : beginning of line
9.  `C-x 1`      : destroy all windows but the this
10. `C-x 2`     : Split horizontally
11. `C-x 3`     : split vertically
12. `C-x o`     : move to next window
13. `C-x k`     : kill buffer
14. `C-x f`     : find file
15. `C-x C-b`   : Ibuffer (enhanced buffer overview)
16. `C-M-s`     : incremental search using regexp
17. `M-%`       : replace string
18. `C-M-%`     : replace string regexp
19. `C-c C-x`   : end emacs (useful on remote servers)
20. `C-h k`     : describe-keybinding
21. `C-h m`     : man page of the major mode

[Cheatsheet](https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf)

[Make your own keybindings](https://www.masteringemacs.org/article/mastering-key-bindings-emacs)


<a id="org150f7fe"></a>

### Killing and Yanking

-   Also known as <span class="underline">cut</span> and <span class="underline">paste</span>

-   But more general because of the **killring**
    -   `C-w` : Kill   (cut)
    
    -   `M-w` : Saving (copy) to the killring
    
    -   `C-y` : Yank   (paste)

-   The killring can be seen as a <span class="underline">stack</span> with the 60 most recent kills


<a id="org8c051da"></a>

### Rectangles

-   `M-x kill-rectangle`

-   `M-x yank-rectangle`

**Example - Swap columns:**

A   1

B   2

C   3


<a id="orgf725bf1"></a>

## Modes


<a id="org14a34f4"></a>

### Major Modes

-   Every buffer possesses a **major mode**.

-   It determines the editing behavior of Emacs while that buffer is current.

-   It is typically some \`language-mode\` like
    -   **r-mode**
    
    -   **c++-mode**
    
    -   **python-mode**
    
    -   **makefile-mode**
    
    -   **text-mode**
    
    -   **markdown-mode**
    
    -   **pandoc-mode**
    
    -   &#x2026;

-   `M-x <major-mode>` : change the major mode


<a id="orgcf0fb7f"></a>

### Minor Modes

-   A buffer can have several **minor modes**
    -   Auto correction
    
    -   Tab Completion
    
    -   Matching parenthesis
    
    -   Macros
    
    -   &#x2026;


<a id="org8e37469"></a>

# Multiple Cursors

-   <https://github.com/magnars/multiple-cursors.el>

**Example**

X 1.000 0.054 
Y 0.054 1.000 
Z 1.000 0.775 


<a id="orgcc65e5d"></a>

# Dired Mode

Dired is a file browsing system within Emacs

-   `C-x d`            : Open dired mode

-   `S-^`              : Up-directory

-   `a`                : Enter directory

-   `q`                : quit

-   `m`                : mark file

-   `u`                : unmark file

-   `d`                : mark for deletion

-   `x`                : delete files marked for deletion

-   `S-!`              : apply a function to file

-   `C-x C-q`          : enter editing mode

-   `C-c C-c`          : leave editing mode

-   `M-S-! nautilus .` : open nautilus here:


<a id="orgf0e57a4"></a>

# Bookmarks

-   `C-x r m` : Create new bookmark (can be a file or a folder)

-   `C-x r b` : Go to bookmark

-   `C-x r l` : List of all bookmarks


<a id="org63779e1"></a>

# The init.el File

-   When Emacs starts, it initialize your configuration file **.init**
    -   located in the **.emacs** folder.
    
    -   in a fresh install it contains nothing!


<a id="org6070b1e"></a>

## Melpa

-   A package repository for Emacs
    -   <https://melpa.org/#/getting-started>

    (require 'package)
    (add-to-list 'package-archives
    '("melpa-stable" . "https://stable.melpa.org/packages/") t)
    (package-initialize)

-   `M-x package-install <package>`

-   `M-x list-packages`


<a id="org400e4e3"></a>

# AucTex

-   A Tex system in Emacs

-   More to come&#x2026;


<a id="orgb16d3b3"></a>

# Emacs Speaks Statistics

-   [ESS](https://ess.r-project.org/)

-   Support for various statistical analysis languages
    -   **R**
    
    -   **Julia**
    
    -   **SAS**
    
    -   **Stata**
    
    -   **JAGS**

-   inferior ESS (iESS) mode is the REPL (interactive shell) we use


<a id="orga43d9eb"></a>

## R

-   .init -> (reqiure 'ess-rutils)

-   The family of ess-rutils: `C-c C. <to-do>`

-   `C-c C-. o` : rdired

-   `C-c C-s`   : switch process

-   `C-c C-. d` : change the current working directory

-   `C-c C-. r` : list all available pkgs (and intsall some if you want)

-   `C-c C-. m` : remove all R objects in the current session

-   `C-c C-. l` : list all local (installed) pkgs

-   `M-x ess-rutils-rsitesearch` :
    -   Suggestion: Bind to C-c f6

-   The drop-down iESS menu


<a id="org2005f46"></a>

### Debugging


<a id="org8b20d9d"></a>

### Package mode


<a id="orgdddca1a"></a>

### Controlling buffer display

-   3.5 Controlling buffer display


<a id="org8b39af7"></a>

# Polymode

-   Several major modes in one buffer

