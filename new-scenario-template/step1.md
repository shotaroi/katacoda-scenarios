# Why test automation?

In software development, efficiency is one of the most important things to be considered. Thus current trend is to perform testing automatically rather than do it manually. Test automation enables software developers to save time, money and effort, and helps deployment of applications with better quality.    

# Setup a Gradle project

Let's start with making a folder where we can create our code with cucumber testing:

`mkdir cucumber-project`{{execute}}

And enter the new folder:

`cd cucumber-project`{{execute}}

In order to use Cucumber testing, you have to use a build tool, either Gradle or Maven. This tutorial uses Gradle. Let's start setting up a Gradle. We do this by running the following command:

`gradle init`{{execute}}

You have to choose some alternatives:

Let's create a application project `2`{{execute}} with implementation language java `3`{{execute}}, build script DSL Groovy `1`{{execute}} and test framework JUnit4 `1`{{execute}}. 

And set the project name `cucumber-project`{{execute}} and source package name `cucumber.project`{{execute}}.

Great! Gradle is now configured in the folder. You can verify this by doing `ls`{{execute}}, and you will see new gradle files in the directory. 


