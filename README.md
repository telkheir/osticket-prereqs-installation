<p align = "center">
<img src = "https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/dbdca06e-9334-4ed6-9777-59acc6ee63f3">
</p>

<h1> osTicket: Prerequisites and Installation </h1>

This tutorial will walk through the prerequisites and installation of osTicket using IIS webserver, PHP manager for IIS, and MySQL database.

<h2> Environments and Technologies Used </h2>
<ul>
  <li>Virtual Machine (not required)</li>
  <li>IIS</li>
  <li>PHP Manager for IIS</li>
  <li>MySQL</li>
  <li>osTicket</li>
</ul>

<h2> Operating Systems Used </h2>
<ul><li>Windows 10</li></ul>


<h2> Navigation </h2>
<ol>
    <li><a href = "#step_1">Enable ISS</a></li>
    <li><a href = "#step_2">Download and prepare the necessary files</a></li>
    <li><a href = "#step_3">IIS configurations</a></li>
    <li><a href = "#step_4">Finishing up</a></li>
    <li><a href = "#step_5">Cleaning up</a></li>
</ol>


<h2> Installation Steps </h2>

<h3 id = "step_1"> 1. Enable ISS</h3>
<blockquote>
  osTicket requires a web server to host it. This tutorial is going to use IIS to do so.</blockquote> 
  <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;First navigate to Programs in the control panel, and under Programs and Features click on “Turn Windows Features on or off.
<br>
<br>

<img width="960" alt="Capture" src="https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/1cb40865-2d94-437e-a5a3-30194154b1f0">

<br>
<br>

Check Internet Information Services. Navigate to the World Wide Web Services subfolder and under Application Development Features, check CGI to enable support.<br>
Back in the World Wide Web Services folder, open the Common HTTP Features subfolder and enable all the files within. The screenshot below shows all the required enabled files.

<br>

<img width="960" alt="Capture1" src="https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/5d7a3627-d101-4d3b-8317-a54c7e5d0c5b">

<br>
<br>

Click OK to apply these changes.<br>
Check IIS functionality using the localhost loopback address in a web browser. You should see the page below.
<br>
<br>

<img width="960" alt="Capture2" src="https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/a555ceae-eac0-4b02-a704-938159b48a7d">


<br><br>


<h3 id = "step_2"> 2. <a href="https://drive.google.com/drive/folders/1h_l4qu5ab6Mni59enbNSVJqvR2ES1pGF?usp=sharing"> Download the necessary files. </a></h3>
From the files downloaded, install PHP Manager for IIS, the Rewrite module and the VC_redist files.

Create a PHP directory in the hard drive<br>
<br>
<img width="960" alt="Capture3" src="https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/388176a1-266b-4988-8405-7cc2065ca668">
<br>
<br>
Extract the files from the php_7.3.8 file into the newly created PHP folder in the C: drive.

Install the mySQL database server, choosing a "Typical" installation.
The configuration wizard will prompt the user to create a root password.
<br>
<br>
<img width="960" alt="Capture4" src="https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/018e65fa-d168-49e0-87f4-a1488e959be7">


Extract the files in the osTicket folder into c:\inetpub\wwwroot. This will act as the web server's main folder. Rename the 'Upload' folder in this path to 'osTicket'.
From there navigate to c:\inetpub\wwwroot\osTicket\include. Rename the "ost-sampleconfig.php" file to "ost-config.php". <br>
Go to this file's properties and into the "Security" tab. Follow the steps in the video below to configure security properties.


https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/629d45f8-d9df-4363-a7ba-396e8fd9a96f


<br>

Lastly, install HeidiSQL and launch the program. Create a new session and input the root password set up in mySQL. Click Open. Within the database Unnammed, create a new database and name it osTicket.
<br>
<br>

<h3 id = "step_3"> 3. IIS Configurations </h3>
The video below shows how to set up the PHP directory.<br>
<br>



https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/bc5c24f6-5b4c-47ed-9683-8eba843acf90



In the IIS Manager, navigate to "thiscomputer"\Sites\Default Web Site\osTicket. From there, click "PHP Manager", scroll to the bottom, and click "Enable or disable an extension". Enable php_imap.dll, php_intl.dll, and php_opcache.dll.


https://github.com/telkheir/osticket-prereqs-installation/assets/145223639/3f6fb8c8-63a5-45ed-adad-803465c0e63e


After making changes, navigate to the right column and click the link to Browse*:80 (http). The osTicket installer should open a tab in your browser.

<br>

<h3 id = "step_4"> 4.  Finishing up </h3>
Scroll to the bottom of the osTicket installer page and click Continue. The installer will prompt you to name the helpdesk and set up an admin. It will ask you for the mySQL information set up in step 2, the database (osTicket) and the password chosen for the root (username) account.
Input all the information and install the program.

<br><br>
<h3 id = "step_5"> 5. Cleaning up </h3>
  Delete c:\inetpub\wwwroot\osTicket\setup <br>
  Go to c:\inetpub\wwwroot\osTicket\include\ost-config.php and set permissions back to "Read" only.
