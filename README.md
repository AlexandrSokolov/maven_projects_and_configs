
- [Basic maven command options](docs/maven.commands.md)
- [Maven properties](docs/maven.properties.md)
- [Should the mvnw files be added to the repository?](#adding-mvnw-maven-wrapper-scripts-into-git-repository)
- [War project with React](war_react/README.md)


### Adding `mvnw` Maven wrapper scripts into git repository

A `mvnw` Maven wrapper script allows you to run a Maven command without having Maven installed and present on your PATH. 
It does by looking for Maven on your `PATH` and, if not found, 
it downloads and installs Maven in a default location (your user home directory, IIRC).

Advantages to commit them into git repository:
- Allows anyone who clones / checks-out your repo to build your project without having to install Maven first.
- Ensures that the version of Maven in use is the version with which your project is compatible.

Why it could be not the best choice:
- Any given `mnvw` file could be used for multiple, unrelated projects
- A `mnvw` file will almost certainly not be different from one version of your project to another
- A non-technical person who runs these scripts often do not realize that Maven still gets installed into their system.
  And have side effects about which they have no-clue.
- How often non-technical person build your projects? 
  I assume most often projects get built by Jenkins or by developers locally. 
  Both Jenkins and developers should configure or keep under control the Maven version installed.
  As a result, is there enough motivation to get flexibility at the expense of complexity 
  (or additional, probably never used files in the project).

