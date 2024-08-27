# SampleProject for Automation Testing using Selenium (Java)

This project is created for creating repository in github and for learning how to use and edit readme.md file in github. 
This project is only for testing purpose.

To refer github id, [please visit](https://github.com/pranjali-ganvir/SampleProject)


<a href="https://selenium.dev"><img src="common/images/selenium_logo_mark_green.svg" width="180" alt="Selenium Logo"/></a>


The project is made possible by volunteer contributors who've
generously donated thousands of hours in code development and upkeep.


## Contributors

Pranjali
Sita
Geeta
Sonu


## Pre-requisite

Core Java
Selenium Framework
Cucumber
Jenkins
TestNg

These are the requirements to create your own local dev environment to contribute to Selenium.

### All Platforms
* Java JDK version 17 or greater (e.g., [Java 17 Temurin](https://adoptium.net/temurin/releases/?version=17))
  * Set `JAVA_HOME` environment variable to location of Java executable (the JDK not the JRE)
  * To test this, try running the command `javac`. This command won't exist if you only have the JRE
  installed. If you're met with a list of command-line options, you're referencing the JDK properly.

### MacOS
  * Xcode including the command-line tools. Install the latest version using: `xcode-select --install`
  * Rosetta for Apple Silicon Macs. Add `build --host_platform=//:rosetta` to the `.bazelrc.local` file. We are working
  to make sure this isn't required in the long run.

### Windows
Several years ago [Jim Evans](https://www.linkedin.com/in/jimevansmusic/) published a great article on
[Setting Up a Windows Development Environment for the Selenium .NET Language Bindings](https://jimevansmusic.blogspot.com/2020/04/setting-up-windows-development.html);
This article is out of date, but it includes more detailed descriptions and screenshots that some people might find useful.

 Selenium in, or the parent directory of an already cloned Selenium repo
4. Download and execute this script in the powershell terminal: [scripts/dev-environment-setup.ps1]`

#### Option 2: Manual Installation
1. Allow running scripts in Selenium in general:
    ```
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
    ```


## Building

Selenium is built using a common build tool called [Bazel](https://bazel.build/), to
allow us to easily manage dependency downloads, generate required binaries, build and release packages, and execute tests;
all in a fast, efficient manner. For a more detailed discussion, read Simon Stewart's article on [Building Selenium](https://www.selenium.dev/blog/2023/building-selenium/)

Often we wrap Bazel commands with our custom [Rake](http://rake.rubyforge.org/) wrapper. These are run with the `./go` command.

The common Bazel commands are:
* `bazel build` — evaluates dependencies, compiles source files and generates output files for the specified target.
It's used to create executable binaries, libraries, or other artifacts.
* `bazel run` — builds the target and then executes it.
It's typically used for targets that produce executable binaries.
* `bazel test` — builds and runs the target in a context with additional testing functionality
* `bazel query` — identifies available targets for the provided path.

Each module that can be built is defined in a `BUILD.bazel` file. To execute the module you refer to it starting with a
`//`, then include the relative path to the file that defines it, then `:`, then the name of the target.
For example, the target to build the Grid is named `executable-grid` and it is
defined in the `'selenium/java/src/org/openqa/selenium/grid/BAZEL.build'` file.
So to build the grid you would run: `bazel build //java/src/org/openqa/selenium/grid:executable-grid`.

The Bazel documentation has a [handy guide](https://bazel.build/run/build#specifying-build-targets)
for various shortcuts and all the ways to build multiple targets, which Selenium makes frequent use of.

To build everything for a given language:
```shell
bazel build //<language>/...
```

To build just the grid there is an alias name to use (the log will show where the output jar is located):
```sh
bazel build grid
```

To make things more simple, building each of the bindings is available with this `./go` command
```shell
./go <language>:build
```


## Developing

### Java

#### IntelliJ
Most of the team uses Intellij for their day-to-day editing. If you're
working in IntelliJ, then we highly recommend installing the [Bazel IJ
plugin](https://plugins.jetbrains.com/plugin/8609-bazel) which is documented on
[its own site](https://plugins.jetbrains.com/plugin/8609-bazel).

To use Selenium with the IntelliJ Bazel plugin, import the repository as a Bazel project, and select the project
view file from the [scripts](scripts) directory. `ij.bazelproject` for Mac/Linux and `ij-win.bazelproject` for Windows.

