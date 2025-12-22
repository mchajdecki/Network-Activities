<p align="center">
   <img src="https://github.com/mchajdecki/Microsoft-Azure/blob/384f24aee08f6fa733a4029f2da5fd9dc52b2f28/images/microsoft-azure-logo.png" alt="AzureLogo" Width="600px" Height="200px">
<img src="https://github.com/mchajdecki/Performing-Activities-and-Network-Traffic-Analysis/blob/7f1063f0fc2f92abce31cc5090ef871f3ee9442e/images/wireshark.jpeg" alt="WiresharkLogo" Width="600px" Height="200px">
  

</p>
<h2>Performing Activities and Network Traffic Analysis Using Microsoft Azure and Wireshark</h2>
<h3>A hands-on tutorial demonstrating how to use virtual machines to simulate network environments, perform connectivity tests, and analyze network traffic using Wireshark. </h3>
<h2>This tutorial outlines the following</h2>
<ul>

<li><a href="#vm">Creating Resources In Microsoft Azure</a></li>
<li><a href="#wireshark">Installing A Protocol Analyzer - Wireshark</a></li>
<li><a href="#ping">Ping Virtual Machines and devices</a></li>
<li><a href="#firewall">Configuring A Firewall</a></li>
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
    <li>Name the Resource Group.</li>
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
<br/>
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
      <li>Name the Virtual Machine Windows VM for easy identification.</li>
      <li>Select (US) East US2 for region.</li>
      <li>Select the Windows 10 Enterprise LTSC 2021 -x64 Gen 1 for Image.</li>
      <li>Select Standard_D2s_v3 - 2vcpus, 8 GIB memory for Size.</li>
      <li>Create your username and password for this VM that you will be using at Log in.</li>
      <li>Make sure to select the checkbox below before continuing to the next step.</li>
     <li>Click Next: Disks</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/57af34de1972fc0d4049a7830a827b26bdd4ffba/images/Slide-7.jpg" alt="Windows_VM - Slide_7"/>
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
     <li>In the Virtual networ section click the Edit virtual network option. Here is where we will create our own Virtual network.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/57af34de1972fc0d4049a7830a827b26bdd4ffba/images/Slide-9.jpg" alt="Windows_VM - Slide_9"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>Give the new Virtual Network a name - e.g.(Network Activities).</li>
     <li>Delete the current subnet so it shows the message below.</li>
     <li>You must add at least one address space to the virtual network.</li>
     <li>You must add at least one subet to the virtual network.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/55480f575d61f8b1ec1aa802b5e6a81cc322d21d/images/Slide_10.jpg" alt="Windows_VM - Slide_10"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
     <li>Click the Add a subnet option.</li>
     <li>A side box will appear and require you to put in Name and Starting address which will be 10.0.0.0 for this tutorial.</li>
     <li>Click Add to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/092174694d13d5f4b4fec97a31661b75a1d6c775/images/Slide_11.jpg" alt="Windows_VM - Slide_11"/>
</p>
<br>
<hr>


<p>
  <ol type="1">
     <li>Click save to continue.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/1d566078fa6a1fe7f74380cce8b120c7817b7e61/images/Slide_12.jpg" alt="Windows_VM - Slide_12"/>
</p>
<br>
<hr>



<p>
  <ol type="1">
     <li>Observe the newly created Virtual Network.</li>
     <li>Click Review + create to finish creating the Windows Virtual Machine with the new Virtual Network.</li>
  </ol>
</p>
<p>
<img src="https://github.com/mchajdecki/Network-Activities/blob/0cb15007db166c060a46ae790cec250a4a1d53bb/images/Slide_13.jpg" alt="Windows_VM - Slide_13"/>
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
<img src="https://github.com/mchajdecki/Network-Activities/blob/319f4de1aeddf07179cdec7e87854549243f5cd9/images/Slide_14.jpg" alt="Windows_VM - Slide_14"/>
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
<img src="https://github.com/mchajdecki/Network-Activities/blob/712022ea900227da5024d599a1d9163607f9f328/images/Slide_15.jpg" alt="Windows_VM - Slide_15"/>
</p>
<br>
<hr>











