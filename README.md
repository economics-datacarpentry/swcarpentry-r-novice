R for Reproducible Economic Analysis
====================================

An introduction to R for non-programmers using the [Gapminder][gapminder] data.
Please see <https://economics-datacarpentry.github.io/swcarpentry-r-novice/> for a rendered version
of this material, [the lesson template documentation][lesson-example]
for instructions on formatting, building, and submitting material,
or run `make` in this directory for a list of helpful commands.

The goal of this lesson is to teach novice programmers to write modular code
and best practices for using R for data analysis. R is commonly used in many
scientific disciplines for statistical analysis and its array of third-party
packages. We find that many scientists who come to Software Carpentry workshops
use R and want to learn more. The emphasis of these materials is to give
attendees a strong foundation in the fundamentals of R, and to teach best
practices for scientific computing: breaking down analyses into modular units,
task automation, and encapsulation.

Note that this workshop focuses on the fundamentals of the programming
language R, and not on statistical analysis.

A variety of third party packages are used throughout this workshop. These
are not necessarily the best, nor are they comprehensive, but they are 
packages we find useful, and have been chosen primarily for their 
usability.

Maintainers:

* [Tom Wright][wright_tom]
* [Naupaka Zimmerman][zimmerman_naupaka]

[gapminder]: http://www.gapminder.org/
[lesson-example]: https://swcarpentry.github.io/lesson-example
[wright_tom]: http://software-carpentry.org/team/#wright_thomas
[zimmerman_naupaka]: http://software-carpentry.org/team/#zimmerman_naupaka


### Setting up your Windows system for converting R Markdown to Markdown

You will need to install the following software to begin.

1. **Ruby**. Use [RubyInstaller](http://rubyinstaller.org/) to install Ruby on your system. *Ruby 2.4.1-2 (x64)*
was selected at the time of writing this. Make sure that you leave the check box ticked at the end of the installation
process. It is for installing **MSYS2**, which is necessary. After you click *Finish*, the Windows command window will
open with ASCII art saying "RubyInstaller2 for Windows". Select option *3*.
2. **RubyGems**. Follow the instructions on [RubyGems.org](https://rubygems.org/pages/download) to
install the latest Ruby Gems on your system.
3. **Python 3**. [Install Python 3](https://www.python.org/downloads/windows/).

Open *MSYS2 MSYS*. You will get Linux-like terminal window appear defaulting into your home directory.
Enter `ls -a` to see the content of your home directory. You will have to edit the `.bash_profile` file.

Add the following lines at the end of your `.bash_profile` (you can find this in *C:\msys64\home\UUUUUUU*,
where "UUUUUUU" is your Windows username, if you want to edit this file using **WordPad** or alike).

```
export PATH="${PATH}:/c/Program Files/RStudio/bin:/c/Program Files/RStudio/bin/pandoc:/c/Ruby24-x64/bin:/c/Program Files/RRRRRRR/bin:/c/Users/UUUUUUU/AppData/Local/Programs/Python/Python36"
export R_LIBS_SITE="/c/Program Files/RRRRRRR/library:/c/Users/UUUUUUU/LLLLLLL/R/win-library/X.X"
```

**NOTE:** Replace "RRRRRRR" with the folder name of where your R is installed, "UUUUUUU" with your Windows username,
"LLLLLLL" with the location of your local default R directory, and "X.X" with the version number of your R install.

Now you have your Windows system setup to convert the R Markdown files in `_episodes_Rmd` to Markdown, which are
automatically copied to `_episodes`, when executing `make lesson-md`.

### Creating or Editing Lessons

You can create or edit lessons in R Markdown and run `make lesson-md` to convert it to Markdown, which allows
GitHub's Jekyll service to render it into HTML and make it presentable at <https://economics-datacarpentry.github.io/swcarpentry-r-novice/>.

1. Clone this repository onto your computer.

    ```
    git clone -b gh-pages https://github.com/economics-datacarpentry/swcarpentry-r-novice.git
    ```

2. Create or edit lessons in R Markdown. When creating a new lesson in R Markdown, you must include this code chunk
after the header comments.

    ```
    source("../bin/chunk-options.R")
    ```

    Save the files in `_episodes_Rmd`.

3. Open *MSYS2 MSYS* and navigate to the local repository, e.g., `cd /c/Users/UUUUUUU/Documents/R/swcarpentry-r-novice`,
then run `make lesson-md`. The R Markdown files in `_episodes_Rmd` will be converted to Markdown. The resulting Markdown
files will be placed in `_episodes`.

4. Push your changes to the GitHub repo.

    ```
    git push origin gh-pages
    ```
    
5. Give it a few seconds and then visit <https://economics-datacarpentry.github.io/swcarpentry-r-novice/> to verify
your additions or changes.
