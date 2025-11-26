<p align="left">
<img src="https://github.com/mchajdecki/Performing-Activities-and-Network-Traffic-Analysis/blob/7f1063f0fc2f92abce31cc5090ef871f3ee9442e/images/wireshark.jpeg" alt="WiresharkLogo" Width="600px" Height="200px">
  </p>
  <p align="right"
    <img src="https://github.com/mchajdecki/Microsoft-Azure/blob/384f24aee08f6fa733a4029f2da5fd9dc52b2f28/images/microsoft-azure-logo.png" alt="AzureLogo" Width="300px" Height="200px">

</p>
<h2>Performing Activities and Network Traffic Analysis With Wireshark</h2>
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

- Macbook Air - Windows 10 Pro and Linux Ubuntu Virtual Machines
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

  
<br/>

  <br/>
<br/>

<h1 id="resource">Creating a Resource Group</h1>
<h2>A Resource Group is a folder in the cloud that holds virtual machines, virtual networks, storage accounts and other created services.</h2>

<p>
<img src="https://github.com/mchajdecki/Performing-Activities-and-Network-Traffic-Analysis-With-Wireshark/blob/e80288a60a689bf43e5a5fb875e00494e0c3d87e/images/Slide_1.jpg" alt="Creating a Resource Group - Slide_1"/>
</p>
<p>
  <ol type="1">
    <li>Find the Resource Group Option on the home page of the Azure Portal or type in the search box.</li>
    <li>Click on the Resource Group Option to Continue.</li>
  </ol>
</p>
<br />
<hr>

<p>
<img src="https://github.com/mchajdecki/Performing-Activities-and-Network-Traffic-Analysis-With-Wireshark/blob/a93d0c1b45baa55b25610ef0b34ad98b7aa75fb5/images/Slide_2.jpg" alt="Creating a Resource Group - Slide_2"/>
</p>
<p>
  <ol type="1">
    <li>Select the Subscription you are currently using.</li>
    <li>Name the Resource Group.</li>
    <li>Select the appropriate time zone you are located in.</li>
    <li>Click Review + Create on the bottom of the page to continue.</li>
  </ol>
</p>
<br/>
<hr>

<p>
<img src="https://github.com/mchajdecki/Performing-Activities-and-Network-Traffic-Analysis-With-Wireshark/blob/3b9de4e9d29d3bfef370557ac746475482409505/images/Slide_3.jpg" alt="Creating a Resource Group - Slide_3"/>
</p>
<p>
  <ol type="1">
    <li>Click create again to continue.</li>
  </ol>
</p>
<br/>
<hr>

<p>
<img src="https://github.com/mchajdecki/Performing-Activities-and-Network-Traffic-Analysis-With-Wireshark/blob/31461d7d54b43a9d36bba5a6b8259e1b59f89267/images/Slide_4.jpg" alt="Creating a Resource Group - Slide_4"/>
</p>
<p>
  <ol type="1">
    <li>A prompt message will display that the resource group has been successfully created.</li>
    <li>The newly created Resource Group will show up on the Microsoft Azure main portal.</li>
    <li>The Resource Group has been created.</li>  
  </ol>
</p>
<br/>
<hr>


<h1 id="resource">Creating a Virtual Machine (Windows)</h1>
<h2>An Azure Virutal Machine (VM) is a cloud-based virtual computer you can run and manage in Microsoft Azure.</h2>

<p>
<img src="" alt=""/>
</p>
<p>
  <ol type="1">
    <li>Find the Resource Group Option on the home page of the Azure Portal or type in the search box.</li>
    <li>Click on the Resource Group Option to Continue.</li>
  </ol>
</p>
<br />
<hr>





