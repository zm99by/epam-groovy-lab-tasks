# Groovy lab

## How to run and test your code

In this repo there's a docker-compose file with gradle image. To run container,
run in your terminal:
```bash
docker-compose run gradle
```
In this container you can run and test your code. The recommended flow it to
edit `app/src/main/groovy/groovylab/App.groovy` file and then run
```bash
gradle run
```
in the container.

Example of `app/src/main/groovy/groovylab/App.groovy`:
```groovy
package groovylab

class App {
    static void main(String[] args) {
        println Task07.encryptThis("hello world")
    }
}
```

### Tasks
**IMPORTANT!** Please note that **every single** function has to return result
of the calculations, this is crucial for automated testing of your tasks

#### Task 1
`app/src/main/groovy/groovylab/Task01.groovy` - sum 2 numbers. Example:
```groovy
Task01.sum(1,4) == 5
```

#### Task 2
`app/src/main/groovy/groovylab/Task02.groovy` - return a list of input elements, where odd numbers are
multiplied by 3 and even numbers by 2. Example:
```groovy
Task02mulEvenOdd([4,5,6]) == [8,15,12]
```

#### Task 3
`app/src/main/groovy/groovylab/Task03.groovy` - define, whether second list sublist of the first list.
Example:
```groovy
Task03.isSublist([1,2,3], [2,3]) == true
```

#### Task 4
`app/src/main/groovy/groovylab/Task04.groovy` - return n-th element of
[Fibonacci's sequence](https://en.wikipedia.org/wiki/Fibonacci_number). Example:
```groovy
Task04.fib(4) == 3
```

#### Task 5
`app/src/main/groovy/groovylab/Task05.groovy` - define, whether input string have a Ip format. Example:
```groovy
Task05.isIp("10.0.152.164") == true
```

#### Task 6
`app/src/main/groovy/groovylab/Task06.groovy` - find all adults in the input map and return them as map.
Example:
```groovy
Task06.adults([Kate: 24, Alan:16, Osvald: 18]) == [Kate: 24, Osvald: 18]
```

#### Task 7
`app/src/main/groovy/groovylab/Task07.groovy` - you need to encrypt input string. Conditions:
- string is a space separated words
- you need to encrypt each word using following rules:
  * The first letter needs to be converted to its ASCII code
  * The second letter needs to be switched with the last letter
Example:
```groovy
Task07.encryptThis("Hello") == "72olle"
Task07.encryptThis("hello world") == "104olle 119drlo"
```

#### Task 8
`app/src/main/groovy/groovylab/Task08.groovy` - parse input json, find all entries, and return another json
with values where sum of digits in value field equal to 9. Example:
```groovy
Task08.parseAndFilterJson("{\"Kate\":18,\"Alan\":16,\"Osvald\":27}") == "{\"Kate\":18,\"Osvald\":27}"
```

#### Task 9
`app/src/main/groovy/groovylab/Task09.groovy` - execute input string as a system command and return output
(**output must be trimmed using .trim() function**). Example:
```groovy
Task09.exec("date") == "Mon Dec  3 22:40:34 +03 2018"
```

#### Task 10
`app/src/main/groovy/groovylab/Task10.groovy` - perform a URL request to the address, specified in function
and return text output. Example:
```groovy
Task10.urlText("http://httpstat.us/200") == "200 OK"
```

#### Task 11
`app/src/main/groovy/groovylab/Task11.groovy` - you need to insert first input string inside the brackets,
near the number, which equals to the second input parameter (string to be used
as default - `"1() 2() 3()"`). Example:
```groovy
Task11.gstring("test", 2) == "1() 2(test) 3()"
```

#### Calculator
`app/src/main/groovy/groovylab/TaskCalculator.groovy` - function `int exec(string)`, calculate input
expression. Example:
```groovy
TaskCalculator.exec("6(3+1)") == 24
TaskCalculator.exec("1+9/3") == 4
```
