<p align="center">
<img src="https://imgur.com/a/LLASmXd"/>
</p>

<h1>Deploying a VM in Azure</h1>
In this tutorial i will set up a Windows Virtual Machine (VM) in Azure, configure networking, enable remote access, and verify its functionality.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Log in to the Azure Portal
- Navigate to Azure Virtual Machines and create a new VM
- Choose an OS (Windows Server/Linux Ubuntu)
- Configure networking (public/private IP, NSG rules)
- Enable RDP/SSH access
- Install software (e.g., IIS for a web server)
- Test connectivity

<h2>Installation Steps</h2>

<p>
<img src="https://imgur.com/tLtSlIl" height="80%" width="80%"/>
</p>
<p>
First Im going to sign into Azure and type in VM for (Virtual Machine) and create a new VM this is going to be for Windows. 
</p>
<br />

<p>
<img src="https://imgur.com/JxT2LeX"/>
</p>
<p>
Im going to create a new VM, called MyTestVM. For VM name I wrote down MyTestVM, I made sure I was on East US 2, availability options I selected No infrasture, image I did Windows 10 Pro (free), size we would just need Standard 1vcpu the cheapest one.
</p>
<br />

<p>
<img src="https://imgur.com/EOO0VIy" height="80%" width="80%"/>
</p>
<p>
For username and password I picked something I could easily remember. Username: Azureadmin and Password: Password123!. Under networking Im going to Create New VNET. Im creating a new Virtual Network (VNet) because its a private network in the cloud where my resources (like VMs) communicate. By creating a VNet, Im ensuring my VM has a secure, isolated network environment. This prevents direct internet access unless configured. I choose defaul subnet because it divides my network into smaller segments to organize and secure traffic between resources. Each subnet can have its own security rules and settings. Azure automatically creates a default subnet.
</p>
<br />

<p>
<img src="https://imgur.com/1f9Bmjo" height="80%" width="80%"/>
</p>
<p>
After I review and create. Im going to log into my VM via RDP by grabbing my VMs public IP address. 
</p>
<br />

<p>
<img src="https://imgur.com/952eML0" height="80%" width="80%"/>
</p>
<p>
Once logged in, Im going to verify the VM by pulling up PowerShell in my RDP and run ipconfig to check if the VM is running and if the network interfaces are configured correctly. 
</p>
<br />

<p>
<img src="https://imgur.com/CiYQDZV" height="80%" width="80%"/>
</p>
<p>
Then Im going to install a web server like IIS, which is often done to verify the VM's functionality by hosting a basic website. I ran several commands in Powershell (as an admin) to see if the VM is working correctly. I specifically had to run this command in order to install IIS "Enable-WindowsOptionalFeature -Online -FeatureName IIS-WebServerRole -All"
Some othert commands I ran to make sure the VM is running properly was: 
  
- <i>Install-WindowsFeature<i> installs IIS to test the VM’s ability to serve web pages.
- <i>hostname<i> confirms the VM's name.
- <i>ping<i> checks network connectivity.
- <i>Get-PSDrive<i> checks disk space.
- <i>Get-Service<i> helps verify critical services.

<img src="https://imgur.com/CiYQDZV" height="80%" width="80%"/>
</p>
<br />
