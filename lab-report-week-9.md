# The Autograder of all Time
For this lab report, I will be sharing my grading script and some submissions being graded!

Here is my grade.sh code:
```
CPATH=".:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar"
set -e

rm -rf student-submission
git clone $1 student-submission
if ! [[-f $FILE]] 
then
    echo "Sorry, ListExamples.java could not be found."
    exit 1
cd student-submission
javac -cp $CPATH *.java
java -cp $CPATH org.junit.runner.JUnitCore TestListExamples
```

## Errors that occured 
While working on my autograder, I ran into several problems. The first issue was that I received a no JUnit test error when I ran my script, which I found was because the JUnit path I set at the beginning of my script was not in the `student-submission` directory, so I need to either copy the JUnit path into the directory, or I need to compile and run the test outside the directory.