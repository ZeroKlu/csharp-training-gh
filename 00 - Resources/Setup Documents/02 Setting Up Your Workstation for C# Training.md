
---

<div style="text-align:center;padding-top:100px;">
<a href="https://github.com/ZeroKlu">
<img src="./images/zeroklu.png" alt="GitHub - ZeroKlu" style="width:80px;border-radius:40px;">
</a>
</div>

<div style="text-align:center;font-size:16pt;padding-bottom:100px;">
C# and .NET Training - Workstation Setup Guide
</div>

---

<div style="page-break-after: always;"></div>

### Purpose:

Performing development requires a few components to be installed on 
your workstation. For .NET (C#) development, you will need to have 
Visual Studio installed.

For those who have Visual Studio Code installed, we will also review 
setting up that environment for .NET development.

If you want to set up your development environment similar to mine, the 
instructions below will walk you through the setup process. If you’re 
following these steps, it is best to do them in the order presented.

<div style="page-break-after: always;"></div>

### Table of Contents:

* [Prerequisites](#prereq)
* [Install Visual Studio](#vs-install)
* [Prep Your File System](#fs-prep)
* [Set Up Visual Studio](#vs-setup)
* [Create a Sample Application](#app-create)
* [Customize Visual Studio](#vs-customize)
* [Clone the C# Training Repository](#clone-training-repo)
* [Install SQL Server](#sql-install)
* [Install SQL Server Management Studio (SSMS)](#ssms-install)
* [Restore the Sample Database](#db-restore)
* [(optional) Install Codeium for Visual Studio](#codeium-vs)
* [Customize Visual Studio Code](#vscode-customize)
* [(optional) Install Codeium for Visual Studio Code](#codeium-vscode)

<div style="page-break-after: always;"></div>

### <a id="prereq"></a>Prerequisites

Prior to any of the steps listed below, please complete all tasks in the guide 
titled:

[01 Setting Up Your Workstation for Development Training.pdf](./01%20Setting%20Up%20Your%20Workstation%20for%20Development%20Training.pdf)

<div style="page-break-after: always;"></div>

### <a id="vs-install"></a>Install Visual Studio

Microsoft Visual Studio is the industry standard IDE for .NET 
development. While there are alternative platforms, we will be using 
Visual studio throughout the training for both C# and later the Unity 
API.

One very important note: If you are using the Community Edition of 
Visual Studio, you cannot develop, build, or deliver software to 
clients. Commercial use requires a licensed edition. If you believe you 
require a license for visual studio, discuss acquiring one with your 
leadership.

1. In your terminal, run one of the following commands (based on the
    edition you are using):  
    <img src="./images/winget-vs.png" style="width:500px">
    * Community Edition:  
      `winget install Microsoft.VisualStudio.2022.Community`
    * Professional Edition:  
      `winget install Microsoft.VisualStudio.2022.Professional`
    * Enterprise Edition:  
      `winget install Microsoft.VisualStudio.2022.Enterprise`

2. Click "Yes" on the UAC prompt.  
   <img src="./images/vs-uac.png" style="width:200px">

3. First, the Visual Studio Installer will be installed. This component 
   can be used later to modify or update your installation.  
   <img src="./images/vs-inst.png" style="width:200px">

4. This installer will then install Visual Studio 2022.  
   <img src="./images/vs-install.png" style="width:400px">

5. After completion, you will see a “successfully installed” message in 
   the terminal.  
   <img src="./images/vs-success.png" style="width:500px">

> We now need to add some development components to the installation.

6. Click on the start button. Then search for and run the “Visual 
   Studio Installer”  
   <img src="./images/vs-inst-run.png" style="width:100px">

7. You may see an alert like the one below, indicating that an updated 
   version is available. If you do, we’ll update the installation 
   first. If not, you can skip to [step 10](#vs-step-10).  
   <img src="./images/vs-alert.png" style="width:150px">

8. Click the [Update] button and respond “Yes” to the UAC alert  
   <img src="./images/vs-update-uac.png" style="width:200px">

9. The update will run automatically  
   <img src="./images/vs-update.png" style="width:400px">

10. <a href="#vs-step-10"></a>After the update (or immediately, if no 
    update was available), you will see the below options. Click on 
    [Modify] to proceed.  
    <img src="./images/vs-mod.png" style="width:400px">

11. In the left-hand pane, check the box on the “ASP.NET and web
    development” function group.  
    <img src="./images/vs-asp.png" style="width:300px">

12. In the right-hand pane (Installation Details), make sure all of the 
    below options are checked:  
    <img src="./images/vs-asp-opt.png" style="width:200px">

13. Back in the left-hand pane, check the box for “.NET desktop 
    development”  
    <img src="./images/vs-desk.png" style="width:300px">

14. In the right-hand pane (Installation Details), make sure all of the 
    below options are checked:  
    <img src="./images/vs-desk-opt-1.png" style="width:180px">
    <img src="./images/vs-desk-opt-2.png" style="width:200px">

15. Click on “Modify”  
    <img src="./images/vs-modify.png" style="width:200px">

16. As usual, respond “Yes” to the UAC warning:  
    <img src="./images/vs-mod-uac.png" style="width:200px">

> Note: You can install any additional components you want, but the 
> items listed above are sufficient for everything covered in the 
> training course.

17. The Visual Studio components will now install.  
    <img src="./images/vs-mod-inst.png" style="width:400px">

18. After completion, close out of the Visual Studio installer and 
    proceed to the next section.

<div style="page-break-after: always;"></div>

### <a id="#fs-prep"></a>Prep Your File System


