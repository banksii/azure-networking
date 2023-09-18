[IMAGE - banner - some network concept map or wireshark or w/e]

<h1>Inspecting Traffic between Virtual MAchines in Azure</h1>

This tutorial I examine various network traffic protocols between two Azure virtual machines


<h2>Environments and Technologies Used</h2>
    <ul>
      <li>Microsoft Azure</li>
      <li>Virtual Machines (Azure)</li>
      <li>Remote Desktop</li>
      <li>WireShark</li>
    </ul>

<h2>Operating Systems Used</h2>
    <ul>
      <li>Windows 10</li>
      <li>Ubuntu Server 20.04</li>
    </ul>

<h2>Navigation</h2>
    <ol>
      <li><a href = "#step_1">Setting up resources</a></li>
      <li><a href = "#step_2">Observing ICMP traffic</a></li>
      <li><a href = "#step_3">Observing SSH traffic</a></li>
      <li><a href = "#step_4">Observing DHCP traffic</a></li>
      <li><a href = "#step_5">Observing DNS traffic</a></li>
      <li><a href = "#step_6">Observing RDP traffic</a></li>
    </ol>

<h2>Tutorial</h2>
    <ol>
      <li><h3 id = "step_1">Setting up resouces</h3>
          For this lab, we need to create a resource group to set up 2 virtual machines in Azure, one running Windows and the Ubuntu. They need to be in the same region and running on the same network. If you allow the first machine to complete deployment, the second one will be placed in the same network by default. I assigned both machines 2 vcpus and at least 8GB of RAM. Designate each machine a username and password. All other settings can be left on default.
          <br><br>
          [IMAGE - config]
          <br><br>
          Once both machines are done being created, there should be a total of 11 files in the resource group:
              <ul>
                  <li>2 disks</li>
                  <li>2 network interface cards</li>
                  <li>2 network security groups</li>
                  <li>2 public IP addresses</li>
                  <li>2 virtual machines</li>
                  <li>1 virtual network</li>
              </ul>
          <br>
          [IMAGE - all files in azure rg]
      </li>
      <li><h3 id = "step_2">Observing ICMP traffic</h3>
          I accessed the virtual machine running Windows using Remote Desktop and downloaded WireShark onto it.
          <br>
          [IMAGE - wireshark]
          <br>
          WireShark is an open-source packet-analyzer, we will use it to examine how some network protocols work between the two virtual machines we have. Install and open WireShark and allow it to start capturing packets. First, we are going to filter out ICMP traffic only.
          [IMAGE]
          Using the command, ping the private IP of the Ubuntu virtual machine and observe the actions of the ping request in WireShark.
          <blockquote>
              Note: The Ubuntu VM is not connected to the internet, so you can't ping its public IP address.
          </blockquote>
      </li>
      <li><h3 id = "step_3">Observing SSH traffic</h3>
      </li>
      <li><h3 id = "step_4">Observing DHCP traffic</h3>
      </li>
      <li><h3 id = "step_5">Observing DNS traffic</h3>
      </li>
      <li><h3 id = "step_6">Observing RDP traffic</h3>
      </li>
    </ol>
