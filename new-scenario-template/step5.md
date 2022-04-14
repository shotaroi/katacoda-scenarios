# Define the steps in the .feature file and run tests

We must define the steps we have created in the Prime.feature file. We do this in a new file called PrimeStepdefs.java located in the test/java folder. Let's enter that
folder:

`cd`{{execute}}

`cd cucumber-project/src/test/java/cucumber/project`{{execute}}

By doing `ls`{{execute}} we can see that there is already a test file here called AppTest.java. `./cucumber-project/src/test/cucumber/project/AppTest.java`{{open}} We want to replace the code in this file. 

This file defines what should be checked for lines starting with the keyword "Given", "When", and "Then" in the Prime.feature file. It's important that the text in the 
brackets that comes after the keyword is the same as the corresponding text in the Prime.feature file.

<pre class="file" data-filename="./cucumber-project/src/test/cucumber/project/AppTest.java" data-target="replace">
package cucumber.project;

import io.cucumber.java.en.Given;
import io.cucumber.java.en.Then;
import io.cucumber.java.en.When;
import org.junit.jupiter.api.Assertions;

public class AppTest{

    cucumber.project.Prime prime;
    String result;

    @Given("^Create a Prime game play$")
    public void createaPrimegameplay() throws Throwable {
        prime = new cucumber.project.Prime();
    }

    @When("^I play with number (\\d+)$")
    public void iPlayWithNumber(int number) throws Throwable{
        result = prime.play(number);
    }

    @Then("^The result is Prime$")
    public void theResultIsPrime() throws Throwable {
        Assertions.assertEquals(result, "Prime");
    }

    @Then("^The result is NoPrime$")
    public void theResultIsNoPrime() throws Throwable {
        Assertions.assertEquals(result, "NoPrime");
    }
   
}
</pre>

Wow! We are now ready to run the tests! This must be done from the cucumber-project directory. Exit the current one:

`cd`{{execute}}

Enter cucumber-project directory:

`cd cucumber-project`{{execute}}

And run the tests:

`gradle cucumber`{{execute}}

