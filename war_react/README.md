
#### Generate React project

In the war project generate react application from the root folder with:
```bash
$ npx create-react-app my-app && mv my-app react
```

#### Building react application as part of `mvn clean package` command

It is configured with `frontend-maven-plugin` plugin and `react.build.skip` property.

See `pom.xml`

#### Control react application building process

It takes time to build react application.
**If you have built the application at least once**, 
you can skip react app building to speed up the process with `react.build.skip=true`:

```bash
$ mvn clean package -Dreact.build.skip=true
```

#### Issues:

1. You get the error:
```text
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-war-plugin:3.2.3:war ... basedir ...react/build does not exist
```
It means the React app has not been built yet. 
Run: `mvn clean package` without `-Dreact.build.skip=true`

Only then, you could build it as: `mvn clean package -Dreact.build.skip=true`

2. In some cases, the `build` folder is located not in the `react`, but in the `target`. 

Build react application with `npm run build`. Check the location of `build` folder path. 
Make sure it gets built into the `react` root application folder. If not correct it.

3. 