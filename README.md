<p align="center">
   <img src="https://github.com/mchajdecki/Microsoft-Azure/blob/384f24aee08f6fa733a4029f2da5fd9dc52b2f28/images/microsoft-azure-logo.png" alt="AzureLogo" Width="600px" Height="200px">
<img src="https://github.com/mchajdecki/Performing-Activities-and-Network-Traffic-Analysis/blob/7f1063f0fc2f92abce31cc5090ef871f3ee9442e/images/wireshark.jpeg" alt="WiresharkLogo" Width="600px" Height="200px">
  

</p>
<h2>Performing Activities and Network Traffic Analysis Using Microsoft Azure and Wireshark</h2>
<h3>A hands-on tutorial demonstrating how to use virtual machines to simulate network environments, perform connectivity tests, and analyze network traffic using Wireshark. </h3>
<h2>This tutorial outlines the following</h2>
<ul>

<li><a href="#vm">Creating Resources In Azure</a></li>
<li><a href="#login">Logging into Virtual Machine</a></li>
<li><a href="#wireshark">Installing A Protocol Analyzer - Wireshark</a></li>
<li><a href="#ping">Testing connection to Virtual Machines and Devices with Ping</a></li>
<li><a href="#firewall">Configuring A Firewall - Network Security Group</a></li>
<li><a href="#ssh">Observe (SSH) Secure Shell</a></li>
<li><a href="#dhcp">Observe (DHCP) Dynamic Host Configuration Protocol Traffic</a></li>
<li><a href="#dns">Observe (DNS) Domain Name System Traffic</a></li>
<li><a href="#rdp">Observe (RDP) Remote Desktop Protocol Traffic</a></li>
</ul>

<br/>

<h2>A Video Break Down Of Everythig Discussed In This Tutorial</h2>

- ### [YouTube: Performing Activities and Network Traffic Analysis With Wireshark ](link)

<h2>Environments and Technologies Used</h2>

- Macbook Air or Desktop - Windows 10 Pro Virtual Machine - Linux Ubuntu Virtual Machine
- Internet Browser (Google Chrome) for Mac - (Microsoft Edge) Windows VM's
- Microsoft Azure
- Wireshark

<h2>Operating Systems Used</h2>

  - macOS Monterey, Version 12.7.6
  - Windows 10 Pro, Version 22H2 - x64 Gen2 (VM)
  - Linux Ubuntu Server, Version 22.D4 LTS x64 Gen2

 <h2>List of Prerequisites</h2>

 - Windows PC or Mac / Laptop / Desktop
 - Internet Access
 - Microsoft Azure account

<br/>

<hr>

<h1 id="vm">In This tutorial we will be creating the following resources in Microsoft Azure</h1>

- Resource Group
- Windows Virtual Machine
- Linux Virtual Machine
- Virtual Networks and Subnets

<h3>For an in depth rundown on Microsoft Azure visit this <a href="https://github.com/mchajdecki/Microsoft-Azure">Microsoft Azure Full Tutorial</a>

  
<br>
<br>
<br>
<br>



<h1 id="resource"><i>Creating a Resource Group</i></h1>
<h2>A Resource Group is a folder in the cloud that holds virtual machines, virtual networks, storage accounts and other created services.</h2>

<p>
  <ol type="1">
     <li>Navigate to Microsoft Azure main portal.</li>
    <li>Find the Resource Group option on the home page of the portal or type it in the search box.</li>
    <li>Click on the Resource Group option to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/0d868bcca05c7445331d2166f2859dbe266d7b33/images/Slide-1.jpg" alt="Creating a Resource Group - Slide_1"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
    <li>Select the Subscription you are currently using.</li>
    <li>Name the Resource Group.(e.g. NetworkActivities)</li>
    <li>Select the appropriate time zone you are located in.</li>
    <li>Click Review + Create on the bottom of the page to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/6ccb2f4dcc9fdfcf7a8b3c95cd63df5162d60f4d/images/Slide-2.jpg" alt="Creating a Resource Group - Slide_2"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>Click create again to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/6ccb2f4dcc9fdfcf7a8b3c95cd63df5162d60f4d/images/Slide-3.jpg" alt="Creating a Resource Group - Slide_3"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>A prompt message will display that the resource group has been successfully created.</li>
    <li>The newly created Resource Group will show up on the Microsoft Azure main portal.</li>
    <li>The Resource Group has been created.</li>  
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/6ccb2f4dcc9fdfcf7a8b3c95cd63df5162d60f4d/images/Slide-4.jpg" alt="Creating a Resource Group - Slide_4"/>
</p>
<hr>
<br>
<br>
<br>



<h1 id="resource"><i>Creating a Virtual Machine (Windows) + Virtual network</i></h1>
<h2>An Azure Virtual Machine (VM) is a cloud-based virtual computer you can run and manage in Microsoft Azure.</h2>
<h3>In the following steps we are creating a Windows Virtual Machine in Microsoft Azure.</h3>

<p>
  <ol type="1">
    <li>On the home page of Microsoft Azure locate the Virtual Machines Option.</li>
    <li>Click on the Virtual Machines to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/6ccb2f4dcc9fdfcf7a8b3c95cd63df5162d60f4d/images/Slide-5.jpg" alt="Windows_VM - Slide_5"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>Continue by clicking the +Create option.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/57af34de1972fc0d4049a7830a827b26bdd4ffba/images/Slide-6.jpg" alt="Windows_VM - Slide_6"/>
</p>
<br>
<hr>




<p>
  <ol type="1">
      <li>Select the resource group created previously.</li>
      <li>Name the Virtual Machine WindowsVM for easy identification.</li>
      <li>Select (US) East US2 for region.</li>
      <li>Select Windows 10 Enterprise LTSC 2021 -x64 Gen 2 for Image.(Windows 10 Pro or Windows 11 are also ok)</li>
      <li>Select Standard_D2s_v3 - 2vcpus, 8 GIB memory for Size.</li>
      <li>Create your username and password for this VM that you will be using at Log in.</li>
      <li>Make sure to select the checkbox below before continuing to the next step.</li>
     <li>Click Next: Disks</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/ee02a38f1448b712705ade4b63e061c429d1b2f0/images/Slide-7.jpg" alt="Windows_VM - Slide_7"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>Click Next: Networking > to continue</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/57af34de1972fc0d4049a7830a827b26bdd4ffba/images/Slide-8.jpg" alt="Windows_VM - Slide_8"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>In the Virtual networ section click the Create new option. Here is where we will create our own Virtual network.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/4300da12ec6e854a5109d452a31d152530116740/images/Slide-9.jpg" alt="Windows_VM - Slide_9"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>After clicking Create new option, a side box will appear.</li>
     <li>Name the new Virtual Network e.g. NetworkActivities.</li>
     <li>Click Ok to continue</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/ddfa16a68c5bb31778363c0a19fa8067d9d0c722/images/Slide_10.jpg" alt="Windows_VM - Slide_10"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
     <li>The newly created Virtual Network (Networ Activities) will shop up here </li>
     <li>Click Review + create to finish creating the Windows Virtual Machine with the new Virtual Network</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/57ef1ada3c13736b7cbe18051f8bec5dbecb1466/images/Slide_11.jpg" alt="Windows_VM - Slide_11"/>
</p>
<br>
<hr>





<p>
  <ol type="1">
     <li>Wait for the creation of the Windows Virtual machine to finish.</li>
     <li>Deployment succeeded message will display once the creation is successfully completed.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/372aab156a3ca8528efcc8a34ec282bdbf6d8d5c/images/Slide_12.jpg" alt="Windows_VM - Slide_12"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>The newly created Windows Virtual Machine will display on the main page of Microsoft Azure.</li>
     <li>This concludes the creation of the Windows Virtual Machine and the new Virtual Network.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/2f40f818272198754625b7a835eda9b5b36ee4b8/images/Slide_13.jpg" alt="Windows_VM - Slide_13"/>
</p>
<hr>
<br>
<br>
<br>


<h1 id="resource"><i>Creating a Virtual Machine (Linux)</i></h1>
<h2>An Azure Virtual Machine (VM) is a cloud-based virtual computer you can run and manage in Microsoft Azure.</h2>
<h3>In the following steps we are creating a Linux Virtual Machine in Microsoft Azure.</h3>

<p>
  <ol type="1">
    <li>On the home page of Microsoft Azure locate the Virtual Machines Option.</li>
    <li>Click on the Virtual Machines to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/1ae73aa1cb70020babbdc895aca6da42a9ac6eb6/images/Slide_14.jpg" alt="Linux_VM - Slide_14"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
    <li>Continue by clicking the +Create option.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/a56f4e1017b7f9e4d30572090fe6473a1c3aacd6/images/Slide_15.jpg" alt="Linux_VM - Slide_15"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
      <li>Select the resource group created previously.</li>
      <li>Name the Virtual Machine LinuxVM for easy identification.</li>
      <li>Select (US) East US2 for region.</li>
      <li>Select the Ubuntu Server 22.04 LTS - x64 Gen2 for Image.</li>
      <li>Select Standard_D2s_v3 - 2vcpus, 8 GIB memory for Size.</li>
      <li>Create your username and password for this VM that you will be using at Log in.</li>
     <li>Click Next: Disks</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/752e5dc976668c46ed9b1a8d5af612b0e38e1de5/images/Slide_16.jpg" alt="Linux_VM - Slide_16"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>Click Next :Networking > to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/3caa9df2587a214d2888072e0005af5a0ffcfa12/images/Slide_17.jpg" alt="Linux_VM - Slide_17"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
    <li>Make sure to select the previously created new Virtual Network e.g. NetworkActivities.</li>
    <li>Click Review + create to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/cfefedadb939b90b68dea6de0b221a12c6c44916/images/Slide_18.jpg" alt="Linuxs_VM - Slide_18"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>Click Create again to finish creating the Linux Virtual Machine.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/65269d17cf6c0672315cedc8153c8bca0f95252a/images/Slide_19.jpg" alt="Linux_VM - Slide_19"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
     <li>Wait for the creation of the Linux Virtual machine to finish.</li>
     <li>Deployment succeeded message will display once the creation is successfully completed.</li>
     <li>The creation of the Linux Virtual Machine is now complete.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/5cdda28cc5803ec1b027920c9bf89b6bc0a25dc8/images/Slide_20.jpg" alt="Linux_VM - Slide_20"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
     <li>On the home page of the Azure portal you should see all the resources that have been created. </li>
     <li>The Resource Group - Windows Virtual Machine - Linux Virtual Machine - New Virtual Network.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/8ebd71ddac08290d2c664d96f63c9787f4c74da1/images/Slide_21.jpg" alt="Linux_VM - Slide_21"/>
</p>
<br>
<hr>

<p>
  <ol type="1">
     <li>Keep a Notepad or Notes with Log-In information somewhere close by and handy. </li>
     <li>This information will be needed for the next steps which will be Logging In to the Virtual Machine.</li>
     <li>This concludes all the steps in creating all the Resources necessary for Network Testing.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/4bbb0cd988597d74c4d32eff2b9fda37202b2320/images/Slide_22.jpg" alt="Linux_VM - Slide_22"/>
</p>
<hr>
<br>
<br>
<br>



<h1 id="login"><i>Loggin Into A Virtual Machine</i></h1>
<p>
  <ol type="1">
    <li>Navigate to Microsoft Azure main portal.</li>
    <li>Click on the Windows Virtual Machine to gather information for log-in.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/ce31d55d33cc50726de56895ef9ec0c0ffb43b42/images/Slide_23.jpg" alt="Login - Slide_23"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
    <li>On the WindowsVM main page "Overview" locate the Networking section.</li>
    <li>In the Networking section find the Public IP addresss and copy and paste it to your notes.</li>
    <li>This along with the username and password created is needed for logging into the Virtual Machine.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/c29b4bbd6c971c8e2ba954b50d44bd3c5c020f68/images/Slide_24.jpg" alt="Login - Slide_24"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>If you are using Mac - Navigate to the App Store.</li>
    <li>In the App Store search for Windows App and download it.</li>
    <li>Once the Windows App is open the main screen will look like the picture below.</li>
    
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/908b1c41abc875639880056f08abac20f9cb4d4f/images/Slide_25.jpg" alt="Login - Slide_25"/>
</p>
<br>
<hr>




<p>
  <ol type="1">
    <li>Once the Windows App is open click on the + and select the Add PC option from the drop down menu.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/81509d46183a65a9e5eb03dc2c1b84eb824797a0/images/Slide_26.jpg" alt="Login - Slide_26"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>After Clicking + and Add PC - The Add PC box will display.</li>
    <li>In the PC name: - copy and paste the Public IP address that is in the Windows VM - Overview - Networking Section.<br>
       *Take a look back on the second slide in this section for reference.</li>
   <li>Click Add to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/5525ba1f22d4075e59b1348dae0c842e12d7f4cb/images/Slide_27.jpg" alt="Login - Slide_27"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>Once the Add button is clicked a window will go into the Saved PCs section.</li>
     <li>On that window the Added Public IP address will display.</li>
    <li>Double click the window to continue to the next step.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/eb9a82659cae8b5454310faf81fdc2a09d5d4b96/images/Slide_28.jpg" alt="Login - Slide_28"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>A box will display to Enter Your Credentials.</li>
     <li>In this section you will enter the username and password created in the Windows Virtual Machine.</li>
    <li>Double click the window to continue to the next step.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/a7c6263f5f3c6533ab0909dc4fb7a3357cade12e/images/Slide_29.jpg" alt="Login - Slide_29"/>
</p>
<br>
<hr>

<p>
  <ol type="1">
     <li>If all the information in the previous steps is filled out correectly - IP Address - Username and Password.</li>
     <li>The Microsoft Windows welcome screen will display.</li>
    
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/a55f28abce071d97f3a72bc2333e5d27be3b32b0/images/Slide_30.jpg" alt="Login - Slide_30"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>On the following screen it will state Choose privacy settings for your device.</li>
     <li>Select all options to no for the purpose of this tutorial.</li>
    
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/1014309082029b773160fc4af3c4468cfaa11756/images/Slide_31.jpg" alt="LogIn - Slide_31">
</p>
<br>
<hr>


<p>
  <ol type="1">
     <li>This is the main home screen of Microsoft Windows.</li>
     <li>You have succesfully logged into the Windows Virtual Machine.</li>
     <li>The Log in process is complete.</li>
    
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/d051a3cd55cd7c9164aded36cf37ed021a126653/images/Slide_32.jpg" alt="LogIn - Slide_32">
</p>
<hr>
<br>
<br>
<br>


<h1 id="wireshark"><i>Installing A Protocol Analyzer - Wireshark</i></h1>
<h2>Wireshark is a free, open-source network protocol analyzer used to capture and inspect data packets in real-time for troubleshooting and security analysis.</h2>

<p>
  <ol type="1">
     <li>On the home page of the logged in Windows Virtual Machine navigate to the Microsoft Edge browser and double click to open it.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/c14a70c9e3e22b546d103d8464f83900ebce91c4/images/Slide_33.jpg" alt="Wireshark- Slide_33"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>Once you are in the Microsoft Edge browser navigate to the <a href="https://www.wireshark.org" target="_blank" >www.wireshark.org</a> website.</li>
     <li>The Wireshark home page will display.</li>
     <li>On the home page of Wireshark click on the Download Now option.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/9871a581c85de9bb6ce60f4b4c8483d08f8505d1/images/Slide_34.jpg" alt="Wireshark - Slide_34"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
    <li>Select the Windows x64 Installer to download.</li>
     <li>The download window will show up on the right hand side of the page.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/b13bdc94b6d9be25b982c64a054a5a56460b87ef/images/Slide_35.jpg" alt="Wireshark - Slide_35"/>
</p>
<br>
<hr>




<p>
  <ol type="1">
    <li>Locate the downloaded file; This PC  ➡️  Downloads.</li>
     <li>Double click to begin installation.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/2168a084986980b1b0e70815e32d65dd3570a196/images/Slide_36.jpg" alt="Wireshark - Slide_36"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
    <li>Continue through the Wireshark Installation steps.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/51560a69d1de981cd018a0f3822a44ecacd7909e/images/Slide_37.jpg" alt="Wireshark - Slide_37"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
    <li>Search for Wireshark Application and open it.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/729053c9ff2c05a0304269cc85e1e4784fe77ea8/images/Slide_38.jpg" alt="Wireshark - Slide_38"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
    <li>This is what the home portal of the Wireshark Application will look like.</li>
     <li>To start a packet capture - have the Ethernet adapter selected and click on the blue shark fin in the the top left corner to begin capture.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/4a2d036e569dd1f5a234d07e77d96592c508c069/images/Slide_39.jpg" alt="Wireshark - Slide_39"/>
</p>
<br>
<hr>




<p>
  <ol type="1">
    <li>Once the packet capture begins you will see all the traffic thats happening on the back end of the computer you are using.</li>
     <li>An IP packet is a small chunk of data sent over the internet that contains both the information being transferred and the necessary details like (addresses) for getting it to the right destination.</li>
     <li>The Wireshark sofware will capture the analysis from performing other various network tests.</li>
     <li>This concludes the download and installation of Wireshark.</li>
</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/a7a01eda2dcf0ca2eb107e68f08bc6a6a2eac787/images/Slide_40.jpg" alt="Wireshark - Slide_40"/>
</p>
<br>
<br>
<br>
<hr>





<h1 id="ping"><i>Testing connection to Virtual Machines and Devices with Ping</i></h1>
<h2>Ping is a network tool that sends a "handshake" signal to another device to see if it is online and measure how fast it responds.</h2>

<p>
  <ol type="1">
     <li>First we have to gather some information in order to use Ping.</li>
     <li>Navigate to Microsoft Azure main portal.</li>
    <li>Locate and click on the Linux VM.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/7880ef525f6c868aa0d0fb0771b91f30b6d52dec/images/Slide_41.jpg" alt="Ping - Slide_41"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>In the overview page of the Linux VM locate the Private IP address.</li>
     <li>Save it in your notes as we will use this IP address to ping from Windows VM to the Linux VM.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/a7bd11307dc84f3fca4eca8d6c07ce75717f0665/images/Slide_42.jpg" alt="Ping - Slide_42"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
     <li>Go back to the Windows Virtual Machine and Wireshark to start a new packet capture.</li>
     <li>To start a packet capture have the Ethernet adapter selected and click on the blue shark fin.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/11f84b74222e0fdf6c1afa8f1a658f91fcdcf9d9/images/Slide_43.jpg" alt="Ping - Slide_43"/>
</p>
<br>
<hr>

<p>
  <ol type="1">
     <li>In the search box filter in Wireshark filter for ICMP traffic only.</li>
     <li>ICMP (Internet Control Message Protocol) is the specialized "language" that network devices use to send status updates, report errors, and check if a destination is reachable. This will show the ping we are attempting</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/614493e4d97a9053760a8efb42202ca6fe2c8d06/images/Slide_44.jpg" alt="Ping - Slide_44"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
     <li>Keep filtering for ICMP (Internet Control Message Protocol) in Wireshark.</li>
     <li>Search for and open up Windows PowerShell.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/02b4e51aa1155c3ac574808d9e1996e5c8f32bd4/images/Slide_45.jpg" alt="Ping - Slide_45"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>In the Powershell Window type in the "ping" command plus the private IP address gathered from the Linux Virtual Machine.</li>
     <li>Then press Enter to run the command.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/22bb3bcac9b9c9637bef157ef3a574703bbb7797/images/Slide_46.jpg" alt="Ping - Slide_46"/>
</p>
<br>
<br>
<br>
<hr>


<p>
  <ol type="1">
     <li>After we run the command in Powershell we see that it shows a successful connection where the Windows VM sends a "request" and the Linux VM sends a "reply", confirming both machines are talking to each other with zero data loss.</li>
     <li>Wireshark acts as a digital observer, capturing every ICMP packet to provide a visual "transcript" of the conversation between your Windows and Linux virtual machines.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/9914966483a74b47b24f24e3a398cb86bec68ddf/images/Slide_47.jpg" alt="Ping - Slide_47"/>
</p>
<br>
<hr>



<h1 id="firewall"><i>Configuring A Firewall - Network Security Group</i></h1>
<h2>Implementing an Inbound Security Rule to successfully deny ICMP traffic on a virtual machine.</h2>
 <p>
    <ol type="1">
       <li>Open Wireshark, start a new packet capture and filter for ICMP traffic only.</li>
       <li>Open Windows Powershell and type in the continue ping command which is (ping + IP address + -t) click enter to run the command. </li>
 </p>
 <p>
    <img src="https://github.com/mchajdecki/Network-Activities/blob/fab4af9a64e7e17b58e5845741641353a7c96bcd/images/Slide_48.jpg" alt="Firewall - Slide_48"/>
 </p>
 <br>
 <hr>


