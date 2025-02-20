# In Class Problem Set 3

I used ComboBoxDemo.java a few years ago.  It used to compile cleanly.  Even though the code has not changed, it now  will not compile without throwing warnings.

Doing everything from a command prompt or Git Bash (no IDEs allowed), your mission is to debug the code and find out why it stopped compiling cleanly.  When you have figured it out,  note what you changed and why it stopped working in the README.md file.


**Changes to code**


**What caused it to stop working?**
What caused it to stop working was the line where we are initializing cBox1. After doing javac along with -Xlint:unchecked ComboBoxDemo.java, I was able to find that this was the line the program was having a problem with. It was saying that I was making an unchecked call to JComboBox(E[]) as a member of the raw type JComboBox where E is a type variable. I figured that if I were to specify that our JComboBox was of type string, the issue would be resolved. So I modified the line to be ---> cBox1 = new JComboBox<String>(s1); This solved the issue as JComboBox was expecting a specified data type. 
