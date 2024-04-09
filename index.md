# Index
> Lab Reports

### Lab Report 1
---

**1. `cd` command**
- Share an example of using the command with no arguments:  
  <img width="390" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/99e9b069-5527-4843-8a54-d3e47ca6a724">  

 The absolute path before using the `cd` command was `/Users/samuelmai/lecture1`.  
 The reason that the output of running `cd` was `/User/samuelmai` is because when we run `cd` with no argument it changes directory to our  home directory. In this case, it led us to exit our lecture1 file and return to the home directory.  
 The output is not an error.  

- Share an example of using the command with a path to a directory as an argument:  
  <img width="495" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/7b7d7f2a-df89-4f44-8d4c-9319353043c2">

  The absolute path before running our command was `/Users/samuelmai`.  
  Our output of `/Users/samuelmai/lecture1` was because we specified where we wanted to change directory into. In this case we ran `cd lecture1` which was in our `samuelmai` folder and changed directories to the `lecture1` folder.  
  There was no error because of the fact that a `lecture1` folder existed in the `samuelmai` folder. As well as the fact that lecture1 is a directory.  

- Share an example of using the command with a path to a file as an argument:
  <img width="629" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/6209fe23-e096-49f7-a71e-ad177630447d">  
  The absolute path before running our command was `/Users/samuelmai`.  
  As we can see, we didn't get an output because of an error. The error is because we used a change directory command but gave it a path to a file as an argument.  
  We get an error because we tried to change directories to a non-directory. Therefore we get a *Not a directory* error.  


---

**2. `ls` command**
   
- Share an example of using the command with no arguments:
  
  <img width="398" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/3ced4c63-54f7-4615-a45a-ba8c6546bac7">  
  Our absolute path before running the command is `/Users/samuelmai/lecture1`.  
  Our output is the list of all the files and folders in our `lecture1` folder. So we are able to see our `Hello.class`, `Hello.java`,   `README`, `messages` listed.  
  The output doesn't have any errors.  

- Share an example of using the command with a path to a directory as an argument:
  
  <img width="500" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/b2039b17-06fe-4edf-aea6-1af25d46aea6">
  
  Our absolute path before running the command is `/Users/samuelmai`.  
  Our output is a list of all the contents found in our `lecture1` folder. This is because we specify the path of the directory that we want to list all the files and directories for.  
  We don't get any errors because the directory path is valid and exists.  

- Share an example of using the command with a path to a file as an argument:
  
  <img width="633" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/9245ab7e-b275-4776-938f-f8ce145c43a7">  

  Our absolute path before running the command is `/Users/samuelmai`.  
  Our output was `/Users/samuelmai/lecture1/messages/zh-cn.txt` which is the exact filepath that we used as an argument. The reason for this is because it's not a directory so it has no content (files or subdirectories) to list.  
  We don't have any errors here, our filepath exists and works.  

  
---

**3. `cat` command**
   
- Share an example of using the command with no arguments:
  
  <img width="379" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/c7ef001e-e271-446e-9c87-e4733eac2671">  

  Our absolute path before running the command is `/Users/samuelmai/lecture1`.  
  Our output is nothing because we don't give the `cat` command a file to work with. In which case we just get a blank environment. Even though we have files in our current working directory, we don't specify a file so `cat` displays nothing.  
  There are no errors in our output.  

- Share an example of using the command with a path to a directory as an argument:
  <img width="641" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/1d202634-aa71-4e7f-a7d4-8f81b56b8052">  
  Our absolute path before running the command is `/Users/samuelmai/lecture1`.  
  Our output is an error. The error is due to the fact that the `messages` directory is not a file. It's a directory so the `cat` command spits out an error here.  

- Share an example of using the command with a path to a file as an argument:
  <img width="637" alt="image" src="https://github.com/KawsAndEffect/cse15l-lab-reports/assets/102554089/e673f715-2b72-43e2-a5bc-3f27acc70a24">
  Our absolute path before running the command is `/Users/samuelmai/lecture1`.  
  Our output here is 你好世界. The reason why is because we gave the `cat` command the filepath to `zh-cn.txt` as an argument. This output is the actual file content of the `zh-cn.txt` file.  
  No, we don't have an error, this is because we gave a valid filepath to a file that exists.  
