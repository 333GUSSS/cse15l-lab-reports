# CSE 15L: Logging into a course-specific account on ieng6 Tutorial

## Installing VScode

Go to the website [Visual Studio Code](https://code.visualstudio.com/) and download the appropriate version of VS Code for your type of laptop (MacOS/Windows).

After Installing VS Code you should be able to see a screen similar to this.

![Image](VS_Code_ScreenShot_Opening.png)

Congrats you have successfully installed Visual Studio Code!

## Remotely Connecting

Now that you have VS Code installed we are going to connect to a remote computer using the account provided to you by the school. 

If you are on windows install [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse), if you are on MacOS you can skip this step.

Next, if you do not know your course-specific account you will have to log in [HERE](https://sdacs.ucsd.edu/~icc/index.php). Write down the name of your account which should look something similar to the two dark gray boxes under the "Additional Accounts" category. 

![Image](UCSD_courseaccount.png)

Your course specific account for this class will be the one that begins with "cse15lsp22" the three letters following that string are very important they are what make your account yours. For example mine is "acc".

Here comes the hard part but dont worry you got this!

(IMPORTANT: make sure you reset your password to your course specific account if you havent already. Intruction on how to do so are here in this [PDF](https://cdn-uploads.piazza.com/paste/ktv2gnof3sx5bf/181c3cb053df5cf1ccaf0457f56f12a2e5aa90b139aef8c2ea8fcc590f02fadf/How-to-Reset-your-Password.pdf))

1. Now that you have reset your password you are going to open VS Code and open a new terminal with Ctrl + ` or whatever other method you prefer and type in (remember to change the zz to your specific account name)

ssh cs15lsp22zz@ieng6.ucsd.edu

2. A message will pop up that look like this if you are connecting for the first time type yes and click enter:

Are you sure you want to continue connecting (yes/no/[fingerprint])?

3. When you log in successfully your screen should look like this.

![Image](Successful_login.png)

Congrats your computer(aka. the client) has successfully remotely logged into a computer in the CSE basement(ake. the server). 


## Trying Some Commands
Now lets test out your newly found power. Go ahead and run some commands in the terminal. Some popular commands you can use are: cd, ls, pwd. Feel free to experiment and learn some of the essential commands like cd which stand for "change directory".

Here is an example of me using "cd .." which moved me up a directory and then I input "ls" which list all of the files/directories of the directory I am currently on.

![Image](commands.png)

Congrats, you have learned some basic commands to use on the terminal.


## Moving Files with scp

Now we are going to learn how to move files from your computer onto there server. 

1. Close your terminal and create a new file on VS Code tittled "WhereAmI.java" and in that file you are going to copy and paste the following contents: 

class WhereAmI {
 public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}

Make sure to add appropriate spacing so that the contents appear in this manner:

![Image](copy.png)

2. Open a new terminal and compile your file with "javac" and run it with "java". 

3. In that same terminal you are going to input the following line (remember to use your specific account username):

scp WhereAmI.java cs15lsp22zz@ieng6.ucsd.edu:~/

4. The terminal will ask for a password, input the came password you put when you log in to the server. 

5. Once you finish step 4 you will need to log into the server using ssh, if you forgot how to log in return to the step titled "Remotely Connecting".

6. Now that you are logged in you are going to type "ls" into the terminal to confirm that the "whereAmI.java" file copied and pasted correcty from the client to the server. Then type "javac WhereAmI.java" and java WhereAmI.java" each on its own line in the terminal. 

(If done correctly you should recieve and terminal similar to the following image but keep in mind I will have a different output then your since I have a different account.)

![Image](scp.png)

Congrats you have successfully copied and pasted a file from your computer onto the server. 

## Setting an SSH Key


## Optimizing Remote Running

