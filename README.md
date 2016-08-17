**Clojure download**

http://clojure.org/community/downloads

**Clojure source code**

https://github.com/clojure/clojure

**IntelliJ Plugin**

https://cursive-ide.com/

# Installation

**Requirements**

Java 1.6 or higher

### Clojure REPL

As Clojure is written in Java and is distributed in a JAR file, find the downloaded prebuilt Clojure JAR file and run *clojure.main* to get the REPL

```sh
$ java -cp clojure-1.8.0.jar clojure.main
```

To see command line options for the `clojure.main` entry point

```sh
$ java -cp clojure-1.8.0.jar clojure.main --help
```

**Online REPL**

To quickly tryout clojure, use a basic version of Clojure REPL at http://www.tryclj.com/ (Be aware of the Clojure version that it uses)

**Leiningen**

Leiningen (https://github.com/technomancy/leiningen) is the standard dependency management tool of the Clojure project. It helps to manage projects (Clojure programs and libraries with multiple entry points and dependencies) and their deployment processes. It provides a Clojure interface to the best parts of the Maven build tool. 

Follow the instructions on the github page and get the lein script, save it to a file and name it 'lein', add its path to the Windows PATH and run the following in the shell

```sh
MINGW64 ~
$ lein
Downloading Leiningen to /c/Users/droid/.lein/self-installs/leiningen-2.6.1-standalone.jar now...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100   605    0   605    0     0    806      0 --:--:-- --:--:-- --:--:--   823
100 14.6M  100 14.6M    0     0  2367k      0  0:00:06  0:00:06 --:--:-- 3011k
Leiningen is a tool for working with Clojure projects.

Several tasks are available:
change              Rewrite project.clj by applying a function.
check               Check syntax and warn on reflection.
classpath           Print the classpath of the current project.
clean               Remove all files from project's target-path.
compile             Compile Clojure source into .class files.
deploy              Build and deploy jar to remote repository.
deps                Download all dependencies.
do                  Higher-order task to perform other tasks in succession.
help                Display a list of tasks or help for a given task.
install             Install the current project to the local repository.
jar                 Package up all the project's files into a jar file.
javac               Compile Java source files.
new                 Generate project scaffolding based on a template.
plugin              DEPRECATED. Please use the :user profile instead.
pom                 Write a pom.xml file to disk for Maven interoperability.
release             Perform :release-tasks.
repl                Start a repl session either with the current project or standalone.
retest              Run only the test namespaces which failed last time around.
run                 Run a -main function with optional command-line arguments.
search              Search remote maven repositories for matching jars.
show-profiles       List all available profiles or display one if given an argument.
test                Run the project's tests.
trampoline          Run a task without nesting the project's JVM inside Leiningen's.
uberjar             Package up the project files and dependencies into a jar file.
update-in           Perform arbitrary transformations on your project map.
upgrade             Upgrade Leiningen to specified version or latest stable.
vcs                 Interact with the version control system.
version             Print version for Leiningen and the current JVM.
with-profile        Apply the given task with the profile(s) specified.

Run `lein help $TASK` for details.

Global Options:
  -o             Run a task offline.
  -U             Run a task after forcing update of snapshots.
  -h, --help     Print this help or help for a specific task.
  -v, --version  Print Leiningen's version.

These aliases are available:
downgrade, expands to upgrade

See also: readme, faq, tutorial, news, sample, profiles, deploying, gpg,
mixed-source, templates, and copying.

```

**Lein tasks**

Run the lein script to see the list of available tasks

```sh
MINGW64 ~
$ lein
Leiningen is a tool for working with Clojure projects.

Several tasks are available:
change              Rewrite project.clj by applying a function.
check               Check syntax and warn on reflection.
classpath           Print the classpath of the current project.
clean               Remove all files from project's target-path.
compile             Compile Clojure source into .class files.
deploy              Build and deploy jar to remote repository.
deps                Download all dependencies.
do                  Higher-order task to perform other tasks in succession.
help                Display a list of tasks or help for a given task.
install             Install the current project to the local repository.
jar                 Package up all the project's files into a jar file.
javac               Compile Java source files.
new                 Generate project scaffolding based on a template.
plugin              DEPRECATED. Please use the :user profile instead.
pom                 Write a pom.xml file to disk for Maven interoperability.
release             Perform :release-tasks.
repl                Start a repl session either with the current project or standalone.
retest              Run only the test namespaces which failed last time around.
run                 Run a -main function with optional command-line arguments.
search              Search remote maven repositories for matching jars.
show-profiles       List all available profiles or display one if given an argument.
test                Run the project's tests.
trampoline          Run a task without nesting the project's JVM inside Leiningen's.
uberjar             Package up the project files and dependencies into a jar file.
update-in           Perform arbitrary transformations on your project map.
upgrade             Upgrade Leiningen to specified version or latest stable.
vcs                 Interact with the version control system.
version             Print version for Leiningen and the current JVM.
with-profile        Apply the given task with the profile(s) specified.

Run `lein help $TASK` for details.

Global Options:
  -o             Run a task offline.
  -U             Run a task after forcing update of snapshots.
  -h, --help     Print this help or help for a specific task.
  -v, --version  Print Leiningen's version.

These aliases are available:
downgrade, expands to upgrade

See also: readme, faq, tutorial, news, sample, profiles, deploying, gpg,
mixed-source, templates, and copying.
```

**lein new task**

The *lein new* task creates a directory structure for a new Clojure project along with a basic configuration file *project.clj*.  

```sh
$ lein new
Generate scaffolding for a new project based on a template.

If only one argument is passed to the "new" task, the default template
is used and the argument is used as the name of the project.

If two arguments are passed, the first should be the name of a template,
and the second is used as the name of the project, for example:

    lein new $TEMPLATE_NAME $PROJECT_NAME

To generate to a directory different than your project's name use --to-dir:

    lein new $TEMPLATE_NAME $PROJECT_NAME --to-dir $DIR

By default, the "new" task will not write to an existing directory.
Supply the --force option to override this behavior:

    lein new $TEMPLATE_NAME $PROJECT_NAME --force
    lein new $TEMPLATE_NAME $PROJECT_NAME --to-dir $DIR --force

Arguments can be passed to templates by adding them after "new"'s options. Use
`--` to separate arguments to lein new and the actual template you are using:

    lein new $TEMPLATE_NAME $PROJECT_NAME --to-dir $DIR -- template-arg-1 template-arg-2

If you'd like to use an unreleased (ie, SNAPSHOT) template, pass in --snapshot:

    lein new $TEMPLATE_NAME $PROJECT_NAME --snapshot

If you'd rather like to use a specific version of template, specify the version
with --template-version option:

    lein new $TEMPLATE_NAME $PROJECT_NAME --template-version $TEMPLATE_VERSION

If you use the `--snapshot` or `--template-version` argument with template args
you may need to use `--` to prevent template args from being interpreted as
arguments to `lein new`:

    lein new $TEMPLATE_NAME $PROJECT_NAME --snapshot -- template-arg-1 template-arg-2

Third-party templates can be found at https://clojars.org/search?q=lein-template.
When creating a new project from a third-party template, use its group-id
as the template name. Note that there's no need to "install" a given third-
party template --- lein will automatically fetch it for you.

Use `lein new :show $TEMPLATE` to see details about a given template.

To create a new template of your own, see the documentation for the
lein-new Leiningen plug-in.

Subtasks available:
default    A general project template for libraries.
plugin     A leiningen plugin project template.
app        An application project template.
template   A meta-template for 'lein new' templates.

Run `lein help new $SUBTASK` for subtask details.

Arguments: ([project-name] [template project-name [-- & args]])
```

Creating a new application project with the *app* template

```sh
$ lein new app BasicProject
Project names containing uppercase letters are not recommended
and will be rejected by repositories like Clojars and Central.
If you're truly unable to use a lowercase name, please set the
LEIN_BREAK_CONVENTION environment variable and try again.

$ lein new app basicproject
Generating a project called basicproject based on the 'app' template.

$ cd basicproject/
```

A snapshot of the directory structure and the content generated by the *app* template:

The default configuration file generated has the following content:

*basicproject/project.clj*

```clj
(defproject basicproject "0.1.0-SNAPSHOT"
  :description "FIXME: write description"
  :url "http://example.com/FIXME"
  :license {:name "Eclipse Public License"
            :url "http://www.eclipse.org/legal/epl-v10.html"}
  :dependencies [[org.clojure/clojure "1.8.0"]]
  :main ^:skip-aot basicproject.core
  :target-path "target/%s"
  :profiles {:uberjar {:aot :all}})
```

The configuration file contains a single call to *defproject*, which is defined by *lein* DSL. The *defproject* call accepts a number of the following parameters: 

1. Project name
2. Project Version
3. A number of keyword parameters

The first parameter passed is the name of the project 'basicproject'.
The second parameter is the version number '0.1.0-SNAPSHOT'. The 'SNAPSHOT' in the version implies that the version is not released and might not be official. 
The following parameters after the version number parameter are the keyword parameters. These include

* description
* url
* license
* dependencies: where the JAR dependencies that should be downloaded from a Maven repository needs to be specified.
* main
* target-path
* profiles

**lein repl task**

Running *lein repl* task first runs a task called *deps* to download the dependency JAR files to the *m2* directory stored in the user's home directory. The *deps* task connects to the default Maven repository (the default Maven repository that *lien* connects to is http://clojars.org) as well as other repositories specified in the *:repositories* parameter of *project.clj* to download the dependencies with the specified versions.

Once the dependencies are downloaded, the REPL runs with the specified dependencies added to the classpath.

```sh
MINGW64 ~
$ lein repl
Retrieving org/clojure/tools.nrepl/0.2.12/tools.nrepl-0.2.12.pom from central
Retrieving org/clojure/pom.contrib/0.1.2/pom.contrib-0.1.2.pom from central
Retrieving org/sonatype/oss/oss-parent/7/oss-parent-7.pom from central
Retrieving clojure-complete/clojure-complete/0.2.4/clojure-complete-0.2.4.pom from clojars
Retrieving org/clojure/clojure/1.8.0/clojure-1.8.0.pom from central
Retrieving org/clojure/tools.nrepl/0.2.12/tools.nrepl-0.2.12.jar from central
Retrieving org/clojure/clojure/1.8.0/clojure-1.8.0.jar from central
Retrieving clojure-complete/clojure-complete/0.2.4/clojure-complete-0.2.4.jar from clojars
nREPL server started on port 51975 on host 127.0.0.1 - nrepl://127.0.0.1:51975
REPL-y 0.3.7, nREPL 0.2.12
Clojure 1.8.0
Java HotSpot(TM) 64-Bit Server VM 1.8.0_91-b15
    Docs: (doc function-name-here)
          (find-doc "part-of-name-here")
  Source: (source function-name-here)
 Javadoc: (javadoc java-object-or-class-here)
    Exit: Control+D or (exit) or (quit)
 Results: Stored in vars *1, *2, *3, an exception in *e

user=>

```

A quick look at the contents of the ~/.m2/ directory

![](_misc/m2%20directory%20contents.png)
