# Create Prime.java

The fucntion we will write is one that checks if the provided number is a prime or not. Let's create a java file for it:

Enter the java folder:

`cd src/main/java/cucumber/project`{{execute}}

Create a java file called Prime.java:

`touch Prime.java`{{execute}}

<pre class="file" data-filename="./cucumber-project/src/main/java/cucumber/project/Prime.java" data-target="replace">
package cucumber.project;

public class Prime {
    public String play(int number){
        if (number < 2) throw new IllegalArgumentException("There are no primenumber less than 2, please provide a larger number");
        for(int i=2; i < number-1; i++){
            if(number % i==0){
                return "NoPrime";
            }
        }
        return "Prime";
    }
}
</pre>


