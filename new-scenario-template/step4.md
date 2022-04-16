# Scenarios - Create Prime.feature

It's finally time to make our cucumber testing file! It should be in the resources directory. Let's enter that folder:

`cd`{{execute}}

`cd cucumber-project/src/test/resources`{{execute}}

Cucumber testing files have the extension `.feature` in which we're going to write our `scenarios`. We create such a file in the resources directory:

`touch Prime.feature`{{execute}}

`.feature` files are written in the `Gherkin language`; a readable way of writing test for beginners and people who are new to programming. The gherkin languages has some
special keywords. First we must write `Feature:` followed by some text. The text should describe what feature of our code we want to test and we therefor write `Prime game play`.
The next keyword is `Scenario:` which should be followed by a text that describes the scenario we want to test. In our case, we want to provide two scenarios; one when the number
we play with is a prime and one when it's not. For the tests we will use the keywords `Given`, `When`, and `Then`, which....

<pre class="file" data-filename="./cucumber-project/src/test/resources/Prime.feature" data-target="replace">
Feature: Prime game play

  Scenario: Play prime to get prime
    Given Create a Prime game play
    When I play with number 5
    Then The result is Prime

  Scenario: Play prime to get noPrime
    Given Create a Prime game play
    When I play with number 10
    Then The result is NoPrime
</pre>

And those lines which starts with keywords such as `Given`,`When`, and `Then` are called `steps` which we're gonna need to define in other file in the next step. 