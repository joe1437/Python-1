<h1> Update a file through a Python algorithm </h1>

<h2>Description</h2>
My organization controls access to restricted content with an allowed list of IP addresses. The "allow_list.txt" file identifies these IP addresses. A separate remove list identifies IP addresses that should no longer have access to this content. I created an algorithm to automate updating the "allow_list.txt" file and remove these IP addresses that should no longer have access.
<br />

<p>
 <h3> Open the file that contains the allow list </h3>
For the first part of the algorithm, I opened the <b>"allow_list.txt"</b> file. First, I assigned this file name as a string to the <b>import_file</b> variable, then, I used a <b>with</b> statement to open the file.  <br/>
  <br/>
 <img src="https://imgur.com/xsTviis.png" height="80%" width="80%" alt="1"/> 
  The <b>with</b> statement is used with the <b>.open()</b> function in read mode to open the allow list file for the purpose of reading it. The purpose of opening the file is to allow me to access the IP addresses stored in the allow list file.
<br />
<br />

<p>
 <h3> Read the file contents </h3>
 In order to read the file contents, I used the <b>.read()</b> method to convert it into the string. <br/>
  <br/>
 <img src="https://imgur.com/TuCQ2fn.png" height="80%" width="80%" alt="1"/> 
 When using an <b>.open()</b> function that includes the argument "r" for “read,” I can call the <b>.read()</b> function in the body of the with statement. The <b>.read()</b> method converts the file into a string and allows me to read it. I applied the <b>.read()</b> method to the file variable identified in the <b>with</b> statement. Then, I assigned the string output of this method to the variable <b>ip_addresses</b>. 
<br />
<br />

<p>
 <h3> Convert the string into a list </h3>
 In order to remove individual IP addresses from the allow list, I needed it to be in list format. Therefore, I next used the <b>.split()</b> method to convert the ip_addresses string into a list  <br/>
 <br/>
 <img src="https://imgur.com/rUHtQvf.png" height="80%" width="80%" alt="1"/> 
 The purpose of splitting ip_addresses into a list is to make it easier to remove IP addresses from the allow list. By default, the <b>.split()</b> function splits the text by whitespace into list elements. In this algorithm, the <b>.split()</b> function takes the data stored in the variable ip_addresses, which is a string of IP addresses that are each separated by a whitespace, and it converts this string into a list of IP addresses. To store this list, I reassigned it back to the variable ip_addresses. 
 <br />
<br />

<p>
 <h3> Iterate through the remove list </h3>
 A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list. To do this, I incorporated a <b>for</b> loop  <br/>
 <br/>
 <img src="https://imgur.com/7GHuiPT.png" height="80%" width="80%" alt="1"/> 
 The <b>for</b> loop in Python repeats code for a specified sequence.
  <br />
<br />

<p>
 <h3> Remove IP addresses that are on the remove list </h3>
First, within my <b>for</b> loop, I created a conditional that evaluated whether or not the loop variable element was found in the <b>ip_addresses</b> list. I did this because applying <b>.remove()</b> to elements that were not found in <b>ip_addresses</b> would result in an error. 
Then, within that conditional, I applied <b>.remove()</b> to <b>ip_addresses</b>. I passed in the loop variable element as the argument so that each IP address that was in the <b>remove_list</b> would be removed from <b>ip_addresses</b>. <br/>
<br/>
 <img src="https://imgur.com/nJQyvzh.png" height="80%" width="80%" alt="1"/> 
  <br />

<p>
 <h3> Update the file with the revised list of IP addresses  </h3>
 As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the <b>.join()</b> method for this. The <b>.join()</b> method combines all items in an iterable into a string so that I could pass it in as an argument to the <b>.write()</b> method when writing to the file <b>"allow_list.txt"</b>. I used the string <b>("\n")</b> as the separator to instruct Python to place each element on a new line. <br/>
 <br/>
 <img src="https://imgur.com/pSGVsmh.png" height="80%" width="80%" alt="1"/> 
 In this case I wanted to write the updated allow list as a string to the file <b>"allow_list.txt"</b>. This way, the restricted content will no longer be accessible to any IP addresses that were removed from the allow list. To rewrite the file, I appended the <b>.write()</b> function to the file object file that I identified in the with statement. I passed in the <b>ip_addresses</b> variable as the argument to specify that the contents of the file specified in the <b>with</b> statement should be replaced with the data in this variable.
   <br />
<br />

<h2>Summary</h2>
I created an algorithm that removes IP addresses identified in a <b>remove_list</b> variable from the <b>"allow_list.txt"</b> file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable <b>ip_addresses</b>. I then iterated through the IP addresses in <b>remove_list</b>. With each iteration, I evaluated if the element was part of the <b>ip_addresses</b> list. If it was, I applied the <b>.remove()</b> method to it to remove the element from <b>ip_addresses</b>. After this, I used the <b>.join()</b> method to convert the <b>ip_addresses</b> back into a string so that I could write over the contents of the <b>"allow_list.txt"</b> file with the revised list of IP addresses.
<br />
