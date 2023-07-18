<h1>Cracking a Password Protected Excel File</h1>


<h2>Description</h2>
For this project, I was given a password protected Excel file and several keywords that were related to the employee that created the file. I was tasked with creating a wordlist using the given keywords and to use the wordlist to try and crack the password.
<br />


<h2>Utilities Used</h2>

- <b>Office2John</b> 
- <b>Bopscrk</b>
- <b>John the Ripper</b>

<h2>Environments Used </h2>

- <b>Kali Linux</b>

<h2>Project walk-through:</h2>

<p>
1. First, I  installed a tool called Office2John. This is a tool that extracts the hash from Microsoft Office documents. <br/>
To run office2john and extract the hash, I ran the following command (protected.xls was the file I extracted the hash from and xlshash.txt is the file the hash was output too):     <br/>
<img src="https://github.com/nataliehoernig1/passwordcracking/assets/139503024/065df0b9-4f37-43bc-a47d-831b152fbfdf" height="80%" width="80%" alt="Password Cracking Steps"/>
<br />
<br />
2. Next, I created a wordlist. I tried making lists with a few different tools that I had installed on Kali Linux, but the one that worked the best was called Bopscrk (Before Outset PaSsword CRacKing). I set the parameters to a minimum of 4 characters and a maximum of 12 characters. Then I entered the keywords I was given into the questions that Bopscrk asks. I set it to use leet transforms (ex.@ instead of “a” or 3 instead of “e”), lowercase/uppercase transforms, and to combine 3 words together at most. It took about 51 minutes and came up with 4,424,782 words. I had it output the wordlist into a text file called wordlist2.txt.  <br/>
<img src="https://github.com/nataliehoernig1/passwordcracking/assets/139503024/0b576410-6a01-4718-ac43-3fd3c2d952b3" height="80%" width="80%" alt="Password Cracking Steps"/>
<br />
<br />
3. Last, I used the John the Ripper tool. To compare the wordlist I created with Bopscrk to the hash file I got from Office2John, I put in the command:
	John --wordlist=(path to wordlist2.txt) (path to xlshash.txt)
	Here is what it looked like when I ran the command, and it found the password. Where I crossed out in gray is where it gave me the password in orange writing. 
  <br/>
<img src="https://github.com/nataliehoernig1/passwordcracking/assets/139503024/bea49bc1-a652-4972-bce2-9629d62dfa38" height="80%" width="80%" alt="Password Cracking Steps"/>
</p>




<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
