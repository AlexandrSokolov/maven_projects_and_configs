
| Purpose                                      | Command                                                                              |     
|:---------------------------------------------|:-------------------------------------------------------------------------------------|
| Verbose mode                                 | `mvn -X -e`                                                                          | 
| Offline Mode                                 | `mvn -o`                                                                             | 
| Force maven update                           | `mvn -U`                                                                             | 
| Skip test compilation and execution          | `mvn -Dmaven.test.skip=true`                                                         | 
| Skip test execution                          | `mvn -DskipTests=true`                                                               | 
| Ignore errors                                | `mvn --fail-never`                                                                   | 
| Pass variable, declared in `pom.xml`         | `mvn -Dskip.react.build=true`                                                        | 
| Activate profile by its id                   | `mvn -Pdev1` or `mvn -P dev1`                                                        | 
| Run mvn on Windows in powershell             | `mvn \`-Dmaven.test.skip=true`                                                       | 
| Update versions in multi-module maven projct | `mvn versions:set -DnewVersion=1.2.3 -DprocessAllModules -DgenerateBackupPoms=false` | 



1. Verbose mode.

   -e, --errors, produces execution error messages. 

   -X, --debug, produces execution debug output.
2. Force maven update. 

   It solves `resolution will not be reattempted until the update interval of` issue.
3. Ignore errors

   When you publish to Nexus with `mvn deploy` and the version is not snapshot and is already published, you get the error.
   In some cases it might be avoided. Use `--fail-never` option.

4. Activate profile by its id

   ```xml
   <profile>
      <id>dev1</id>
      <properties>
        <maven.test.skip>true</maven.test.skip>
      </properties>
    </profile>
   ```
   Activate it with: `mvn -Pdev1`

5. Run mvn on Windows in powershell.

   It relates to the encoding of the minus sign in powershell. The solution is to escape it with a backtick (`) symbol.