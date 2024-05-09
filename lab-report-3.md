## Lab Report 3

### Part 1:

1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown).

   ```
  @Test
  public void testAverageWithoutLowest() {
    double[] arr = {1.0, 1.0, 2.0, 3.0};
    double expected = 2.0;
    double actual = ArrayExamples.averageWithoutLowest(arr);
    assertEquals(expected, actual, 0.0001);
  }
   ```

3. An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown).

  ```
  @Test
  public void correctTestAverageWithoutLowest() {
    double[] arr = {2.0, 3.0, 5.0, 7.0};
    double expected = 5.0;
    double actual = ArrayExamples.averageWithoutLowest(arr);
    assertEquals(expected, actual, 0.0001);
  }
  ```

4. The symptom, as the output of running the two tests above (provide it as a screenshot -- one test should pass, one test should fail).

  <img width="834" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/fd5f2b9a-15df-412c-8eb7-b6f016204ae3">


5. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown).

  ```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
  ```

  ```
  static double averageWithoutLowest(double[] arr) {
  if (arr.length < 2) { return 0.0; }
  double lowest = arr[0];
  for (double num : arr) {
      if (num < lowest) { lowest = num; }
  }
  double sum = 0;
  boolean lowestAlreadyRemoved = false;
  for (double num : arr) {
      if (num == lowest && !lowestAlreadyRemoved) {
          lowestAlreadyRemoved = true;
      } else {
          sum += num;
      }
  }
  return sum / (arr.length - 1);
}
  ```

6. Briefly describe (2-3 sentences) why the fix addresses the issue.

  The reason that our original `averageWithoutLowest()` method was buggy was due to the fact that it didn't take into account the case where the lowest number occurs more than once in the array. This resulted in the multiple occurences of the lowest number being excluded from the average calculation. We address this issue by adding in the boolean `lowestAlreadyRemoved` which starts with being assigned `false` and is assigned `true` when `num` == `lowest` AND `lowestAlreadyRemoved` is still false, which means after the first time we encounter the lowest number, it will be excluded and will no longer be excluded any time after.

### Part 2:

***Prompt given to ChatGPT***

Consider the commands less, find, and grep. Choose one of them. Online, find 4 interesting command-line options or alternate ways to use the single command you chose.

Instruction: For each of those options, give 2 examples of using it on files and directories from ./technical. That makes 8 total examples, all focused on a single command. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

ChatGPT's Response:


I chose the command grep, which is a powerful tool used for searching text data sets for lines that match a regular expression. Here are four interesting command-line options for grep:

1. `-i (ignore case)`
This option makes the search case-insensitive, allowing you to find matches regardless of case.

``` grep -i "error" ./technical/logs.txt ```

This command searches for the word "error" in logs.txt within the ./technical directory, ignoring case differences like "Error", "ERROR", etc.

``` grep -i "network" ./technical/config/settings.conf ```

This searches for "network" in the settings.conf file, catching all cases like "Network", "NETWORK", etc., which is useful for configuration files where case usage might vary.

2. `-r (recursive)`
This option allows grep to perform a recursive search through directories.

``` grep -r "function" ./technical/ ```

This command recursively searches for the word "function" in all files under the ./technical directory. It's useful for searching through complex directory structures.

``` grep -r "TODO" ./technical/src/ ```

This searches for "TODO" in all files within the `./technical/src` directory and its subdirectories, helping developers quickly find unfinished tasks.

3. `--include`
This option allows you to specify a pattern for the files to search within, which can be combined with -r for more targeted searching.

``` grep -r --include "*.py" "def" ./technical/scripts/ ```

This command searches for the keyword "def" in all Python files within the `./technical/scripts` directory, useful for finding function definitions in Python scripts.

``` grep -r --include "*.md" "API" ./technical/docs/ ```

This searches for "API" in all Markdown files within the `./technical/docs` directory, which is helpful for reviewing documentation.

4. `-v (invert match)`
This option inverts the match, showing only the lines that do not match the given pattern.

``` grep -v "success" ./technical/logs.txt ```

This command shows all lines in logs.txt that do not contain the word "success", which can be useful for filtering out non-error messages in logs.

``` grep -v "deprecated" ./technical/reports/usage_report.txt ```

This filters out lines that contain the word "deprecated" from the `usage_report.txt`, helping to focus on current features or methods.

These options enhance the utility of `grep` by providing flexible and powerful ways to search through text data across files and directories.


### My answer using inspiration/help from the ChatGPT output:

<img width="1436" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/bc1537ba-50bd-41da-8d66-e711ea812a90">

I chose the command grep, which is a powerful tool used for searching text data sets for lines that match a regular expression. Here are four interesting command-line options for grep:

1. `-i (ignore case)`
This option makes the search case-insensitive, allowing you to find matches regardless of case.

``` grep -i "planes" ./technical/911report/chapter-1.txt ```

**OUTPUT**
<img width="1439" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/a551b5fa-07cf-48d4-8d41-c51c21332709">


This command searches for the word "planes" in `./technical/911report/chapter-1.txt` within the ./technical/911report/chapter-1.txt file, ignoring case differences like "Planes", "PLANES", etc.


``` grep -i "Las Vegas" ./technical/911report/chapter-1.txt ```

**OUTPUT**

<img width="1439" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/5bd82ba2-4c48-4d43-bdf4-b3d09475433a">

This searches for "Las Vegas" in the `./technical/911report/chapter-1.txt` file, catching all cases like "las vegas", "LAS VEGAS", etc.


2. `-r (recursive)`
This option allows grep to perform a recursive search through directories.

``` grep -r "jet" ./technical/911report ```

**OUTPUT**

<img width="1439" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/37a9e943-955a-4042-9bf3-c07862887b38">

This command recursively searches for the word "jet" in all files under the `./technical/911report` directory and its subdirectories. It's useful for searching through complex directory structures.


``` grep -r "commander" ./technical/911report ```

**OUTPUT**

<img width="1440" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/fc78ef9e-836a-45b6-88cf-35d6b3f89f7a">


This recursively searches for "commander" in all files within the `./technical/911report` directory and its subdirectories, that could developers quickly find files using keywords.


3. `--include`
This option allows you to specify a pattern for the files to search within, which can be combined with -r for more targeted searching.

``` grep -r --include "*.py" "def" ./technical/911report ```

**OUTPUT**
<img width="721" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/751d283c-1bf9-4cc0-80ba-6f00e6106c12">

This command searches for the keyword "def" in all Python files within the `./technical/911report` directory, useful for finding function definitions in Python scripts. This would be very helpful if the whole `./technical` directory wasn't a bunch of subdirectories of .txt files. Nothing happened since there are no `.py` files in `911report` subdirectory.

``` grep -r --include "*.txt" "cruel" ./technical/911report ```

**OUTPUT**

<img width="995" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/cd38fc11-becc-463a-8638-ef39474cc68e">

This searches for "cruel" in all Markdown files within the `./technical/911report` directory, which is helpful for reviewing documentation.


4. `-v (invert match)`
This option inverts the match, showing only the lines that do not match the given pattern.

``` grep -v "success" ./technical/911report/chapter-1.txt ```

**OUTPUT**

<img width="1440" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/1c5bc3a6-20c4-4f69-9b59-f2fae23c788a">

This command shows all lines in `./technical/911report/chapter-1.txt` that do not contain the word "success", which can be useful for filtering out non-error messages in logs. In this case its not as useful since its just a `.txt` file instead of a testing file. 

``` grep -v "the" ./technical/911report/chapter-1.txt ```

**OUTPUT**

<img width="1440" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/17680e4d-b885-46aa-b8f7-73d059ce8927">


This filters out lines that contain the word "the" from the `./technical/911report/chapter-1.txt`, helping to focus on lines without "the". This is really cool as we can help filter out certain buzzwords.

***These four options enhance the utility of `grep` by providing flexible and powerful ways to search through text data across files and directories.***
