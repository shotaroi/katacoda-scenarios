# Gradle configuration for Cucumber

It's time to change the build.gradle file so that gradle can understand that we want to use Cucumber. We should add some dependencies, configurations and Cucumber task. The Cucumber task is configured to run the test scenarios written in a feature file in resources directory. We're gonna look at the feature file and test scenarios more in detail later. Let's remove the text in the gradle.build file and replace it with the following: 

<pre class="file" data-filename="./cucumber-project/build.gradle" data-target="replace">
plugins {
    id 'java'
}

group 'org.example'
version '1.0-SNAPSHOT'

repositories {
    mavenCentral()
}

dependencies {
    testImplementation 'org.junit.jupiter:junit-jupiter-api:5.8.1'
    testRuntimeOnly 'org.junit.jupiter:junit-jupiter-engine:5.8.1'
    testImplementation 'io.cucumber:cucumber-java:7.0.0'
}
configurations {
    cucumberRuntime {
        extendsFrom testImplementation
    }
}

task cucumber() {
    dependsOn assemble, testClasses
    doLast {
        javaexec {
            main = "io.cucumber.core.cli.Main"
            classpath = configurations.cucumberRuntime + sourceSets.main.output + sourceSets.test.output
            args = ['--plugin', 'pretty', '--glue', 'cucumber.project', 'src/test/resources']
        }
    }
}
</pre>


