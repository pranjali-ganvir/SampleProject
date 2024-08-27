# SampleProject for Automation Testing using Selenium (Java)

This project is created for creating repository in github and for learning how to use and edit readme.md file in github. 

This project is only for testing purpose.

To refer github id, [please visit](https://github.com/pranjali-ganvir/SampleProject)

## Contributors

* Pranjali
* Sita
* Geeta
* Sonu

## Pre-requisite

- Core Java
- Selenium Framework
- Cucumber
- Jenkins
- TestNg

Selenium is built using a common build tool called [Bazel](https://bazel.build/), to
allow us to easily manage dependency downloads, generate required binaries, build and release packages, and execute tests;
all in a fast, efficient manner. For a more detailed discussion, read Simon Stewart's article on [Building Selenium](https://www.selenium.dev/blog/2023/building-selenium/)


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
 Download and execute this script in the powershell terminal: [scripts/dev-environment-setup.ps1]`
