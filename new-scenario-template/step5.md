# Define the steps in the .feature file and run tests

We must define the steps we have created in the `Prime.feature` file. We do this in a file located in the test project directory. Let's enter that
directory:

`cd`{{execute}}

`cd cucumber-project/src/test/java/cucumber/project`{{execute}}

By doing `ls`{{execute}} we can see that there is already a test file here called AppTest.java. We want to replace the code in this file. 

This file defines what should be checked for lines starting with the keyword `Given`, `When`, and `Then` (steps) in the `Prime.feature` file. It's important that the text in the 
brackets that comes after the keyword is the same as the corresponding text in the `Prime.feature` file.

<pre class="file" data-filename="./cucumber-project/src/test/java/cucumber/project/AppTest.java" data-target="replace">
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

Now you should be able to see that all scenarios and steps are passed :) 

# Benefits of Cucumber

In Cucumber `Behavior-driven development` approach is adopted and it works well for better collaboration between different teams in development, and customers. This is largely thanks to the behavior scenarios which can be written by anyone with plain language. And the `Gherkin language` used for describing the test cases also help the collaboration with its easy to understand style not only for the developer but also for other non-technical persons. 