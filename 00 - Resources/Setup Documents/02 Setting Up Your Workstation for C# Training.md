
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

- [Purpose:](#purpose)
- [Table of Contents:](#table-of-contents)
- [Prerequisites](#prerequisites)
- [Install Visual Studio](#install-visual-studio)
- [Prep Your File System](#prep-your-file-system)
- [Set Up Visual Studio](#set-up-visual-studio)
- [Create a Sample Application](#create-a-sample-application)
- [Customize Visual Studio](#customize-visual-studio)

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

As part of the next section, we will be creating a sample project. 
We’ll need somewhere to place it.

1. On your PC, create a folder called “Visual Studio Projects” (I 
   created mine on the C: root)  
   <img src="./images/vs-proj.png" style="width:100px">

<div style="page-break-after: always;"></div>

### <a id="vs-setup"></a>Set Up Visual Studio

Visual Studio is highly configurable, and we will not be addressing the 
majority of the options here. However, there are several that will make 
the experience easier in training, so we will handle them now.

1. Launch Visual Studio  
   <img src="./images/vs-icon.png" style="width:40px">

2. You will be prompted to log in with your Microsoft account. Click on 
   “Sign In”
   > Note: Do not skip this step, as we need to set up with a Microsoft 
   > account for a later step  

   <img src="./images/vs-signin.png" style="width:400px">

3. On the “Sign in” dialogs, enter the email and password for your 
   Microsoft Account You should already have an MS account associated 
   with the email address you used to obtain your Visual Studio 
   license.  
   <img src="./images/vs-login.png" style="width:300px">

4. Once you have successfully logged in, you will be prompted to select 
   a color theme. I use the default “Dark” theme, but you can configure 
   yours however you like.  
   <img src="./images/vs-theme.png" style="width:200px">  
   Once you select your theme, click on [Start Visual Studio] and 
   continue to the next section

<div style="page-break-after: always;"></div>

### <a id="app-create"></a>Create a Sample Application

Now we need to make sure everything installed properly by creating a 
sample application in Visual Studio.

1. If it’s not already running, launch Visual Studio  
   <img src="./images/vs-icon.png" style="width:40px">

2. On the startup dialog, select the option to “Create a new project”  
   <img src="./images/vs-new.png" style="width:250px">

3. Search for “console” and select the option for “Console App” Then 
   click “Next”  
   <img src="./images/vs-console-app.png" style="width:400px">
   <img src="./images/vs-next.png" style="width:60px">

4. Name the project “HelloWorld”  
   <img src="./images/vs-proj-name.png" style="width:100px">

5. Modify the location to point to the “Visual Studio Projects” folder 
   you created previously, then click [Create]  
   <img src="./images/vs-proj-loc.png" style="width:140px">
   <img src="./images/vs-proj-create.png" style="width:60px">

6. Select ".NET 8.0" for the target framework, then click [Create]
   <img src="./images/vs-proj-fw.png" style="width:160px">
   <img src="./images/vs-proj-create.png" style="width:60px">

7. Add the following code in the Program.cs file that gets created for 
    you (don’t worry about understanding it for now):

    ```csharp
    using System;

    namespace HelloWorld
    {
        internal class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("Hello World!");
                _ = Console.ReadLine();
            }
        }
    }
    ```

    <img src="./images/vs-proj-code.png" style="width:300px">

8. At the top of the screen, click the “Start” button to run the 
   program.  
   <img src="./images/vs-start.png" style="width:60px">

9. You should see the following in a new terminal window:  
   <img src="./images/vs-hello.png" style="width:200px">

<div style="page-break-after: always;"></div>

### <a id="customize-visual-studio"></a>Customize Visual Studio

There are a few optional convenience settings I recommend in Visual 
Studio.

1. In Visual Studio, click on TOOLS > OPTIONS  
   <img src="./images/vs-tools.png" style="width:100px">
   <img src="./images/vs-options.png" style="width:100px">

2. Under “Projects and Solutions,” select “Locations”  
   <img src="./images/vs-loc.png" style="width:200px">

3. Update the paths to use the “Visual Studio Projects” folder you 
   created earlier in the process.  
   <img src="./images/vs-path.png" style="width:300px">

4. Under “Source Control,” select “Git Global Settings”  
   <img src="./images/vs-git.png" style="width:200px">

5. Enter the username and email address you use for Git (these may 
   already be filled in), and change the default location to your 
   “Visual Studio Projects” folder, then click [OK].  
   <img src="./images/vs-git-creds.png" style="width:300px">
   <img src="./images/vs-ok.png" style="width:60px">

<div style="page-break-after: always;"></div>


