# Setup a Gradle project

Let's make a folder where we can create our code with cucumber testing:

`mkdir cucumber-project`{{execute}}

And enter the new folder:

`cd cucumber-project`{{execute}}

In order to use Cucumber testing, you have to use a build tool, either Gradle or Maven. This tutorial uses Gradle. Let's start setting up a Gradle. We do this by running the following command:

`gradle init`{{execute}}

You have to chose some alternatives:

Let's create a application project `2`{{execute}} with implementation language java `3`{{execute}}, build script DSL Groovy `1`{{execute}} and test framework JUnit4 `1`{{execute}}. 

And set the project name `cucumber-project`{{execute}} and source package name `cucumber.project`{{execute}}.

Great! Gradle is now configured in the folder. You can verify this by doing `ls`{{execute}}, and you will see new gradle files in the directory. 


