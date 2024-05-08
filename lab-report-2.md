## Lab Report 2

---

#### Part 1:

`Handler` **Code:**

<img width="610" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/ccbc8a78-2f97-447a-99e5-e030ee547722">


`ChatServer` **Code:**

<img width="823" alt="1" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/534fe1db-9385-4289-bb3a-994dcd1e76ee">


**Using** `/add-message`**:**
<img width="548" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/8900a70e-4c8b-4a72-b60f-dde2292318b7">

* **Which methods in your code are called?**
  In my code, the methods `URLHandler`, `getPath()`, `handleRequest()`, `getQuery()` are called. 
* **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**
  The `URI url` is a relevant argument for the `handleRequest()` method and functions as the input url which is a string with which we then perform if statements. The relevant arguments are the `input` which is what the user is adding onto the website output. It starts as an empty string and as we add more messages it adds onto this input string. It's essentially like our storage. The `parameters` variable stores the users input split in half by the & symbol, which ultimately splits up the message and the user's name. The `phrase` variable is an array that is used to distinguish whether or not we are looking at the message string or the user's name, and is used in a loop splitting at the = symbol. The `message` variable is a string which is used to store the message given by the user. The `user` variable is a string that saves the user's name. These two variables are used to put together the final output which is stored in `result`, and added to the input string.
* **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**
  The `user`, `message`, `parameters`, and `phrase` change after each request, and the `input` is added onto given these new changes, but still contains the original previous messages in order to output a conversation. Before the specific request, the `input`, `user`, and `message` variables start off as empty strings `""`. The `url` variable doesn't change from  before and after handleRequest is executed. `parameters` starts off as the query of the url split by the `&` symbol. After the request is executed, the `input` changes to `jpolitz: Hello`, `user` to `jpolitz:`, `message` to `Hello`, `parameters` to `s=Hello&user=jpolitz`. `phrase` is created as the different values of the `parameters` array, splits by `=` and updates during the loop. After the first loop it stores the value `s=Hello` and splits it at the `=`, saving `Hello` to the message variable. After the second loop `phrase` has the value `user=jpolitz` and splits it at the =, saving `jpolitz` to the user variable.

<img width="607" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/59c3b50d-d689-4f30-bfe4-4ad30b80c959">

* **Which methods in your code are called?**
  In my code, the methods `URLHandler`, `getPath()`, `handleRequest()`, `getQuery()` are called. 
* **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**
    The relevant arguments are the `input` which is what the user is adding onto the website output. It starts as an empty string and as we add more messages it adds onto this input string. It's essentially like our storage. The `parameters` variable stores the users input split in half by the & symbol, which ultimately splits up the message and the user's name. The `phrase` variable is an array that is used to distinguish whether or not we are looking at the message string or the user's name, and is used in a loop splitting at the = symbol. The `message` variable is a string which is used to store the message given by the user. The `user` variable is a string that saves the user's name. These two variables are used to put together the final output which is stored in `result`, and added to the input string.
* **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.** *
    The `user`, `message`, `parameters`, and `phrase` change after each request, and the `input` is added onto given these new changes, but still contains the original previous messages in order to output a conversation. Before the specific request, the `input`, `user`, and `message` variables start off as empty strings `""`. `parameters` starts off as the query of the url split by the `&` symbol. The `url` variable doesn't change from  before and after handleRequest is executed. After the request is executed, the `input` changes to `jpolitz: Hello\nyash: How are you`, `user` to `yash:`, `message` to `How are you`, `parameters` to `s=How are you&user=yash`. `phrase` is created as the different values of the `parameters` array, splits by `=` and updates during the loop. After the first loop it stores the value `s=How are you` and splits it at the =, saving `How are you` to the message variable. After the second loop `phrase` has the value `user=yash` and splits it at the =, saving `yash` to the user variable.


#### Part 2:

1. <img width="565" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/068be536-9e8a-4403-950e-25bf816a893d">


2. <img width="578" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/1e057e1f-3d6b-49c6-8054-42237926d9f4">


3. <img width="686" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/062ccd19-f5b1-4c88-b90f-07e28acf8ba0">



#### Part 3:
I had no idea what a server was and didn't know how to generate an ssh key. We learned how to run a server on a remote computer which is really cool since it allows us to possibly handle larger datasets that would literally be impossible on our local computers that us average students have. 
