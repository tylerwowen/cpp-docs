---
title: "Setting the Path and Environment Variables for Command-Line Builds"
ms.custom: na
ms.date: 10/04/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: get-started-article
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
caps.latest.revision: 17
manager: ghogen
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# Setting the Path and Environment Variables for Command-Line Builds
The Visual C++ command-line build tools require several environment variables that are customized for your installation. When Visual Studio is installed, it creates command files that set the required environment variables, and then creates shortcuts that start a Command Prompt window that already has these variables set. When you want to use the command-line tools, you can run one of these shortcuts, or you can open a plain Command Prompt window and then run the vcvarsall.bat command file.  
  
 The Visual C++ command-line tools use the PATH, TMP, INCLUDE, LIB, and LIBPATH environment variables, and may also use tool-specific environment variables. Because the values of these environment variables are specific to your installation, and can be changed by product updates or upgrades, we recommend that you use vcvarsall.bat or a Developer Command Prompt shortcut instead of setting them yourself. For information about the specific environment variables used by the compiler and linker, see [CL Environment Variables](../VS_visualcpp/CL-Environment-Variables.md) and [LINK Environment Variables](../VS_visualcpp/LINK-Environment-Variables.md).  
  
> [!NOTE]
>  Several command-line tools or tool options require Administrator permission. To use them, we recommend that you open a Command Prompt window by using the **Run as Administrator** option. On Windows 10, right-click to open the shortcut menu for the Command Prompt window, then choose **More**, **Run as administrator**.  
  
## Using the Command Prompt shortcuts  
 Visual Studio installs a Developer Command Prompt shortcut  that opens a Command Prompt window and sets the environment to use the 32-bit x86-native toolset to target x86 processors. If you have installed the Visual C++ Build Tools edition, a Developer Command Prompt shortcut is not installed, but the x86 Native Tools Command Prompt does the same thing.  
  
 Command prompts for 32-bit cross-compilers that target x64 and ARM platforms are also available. On 64-bit platforms, Command Prompt shortcuts for a 64-bit x64-native toolset that targets x64 processors, and for 64-bit cross-compilers that target ARM and x86 processors are installed. These versions of the command-line toolset are available in all editions of Visual Studio:  
  
 x86 Native Tools Command Prompt  
 Use this toolset to create output files for x86 machines. It runs as a 32-bit process, native on an x86 machine and under WOW64 on a 64-bit Windows operating system.  
  
 x86 x64 Cross Tools Command Prompt  
 Use this toolset to create output files for x64. It runs as a 32-bit process, native on an x86 machine and under WOW64 on a 64-bit Windows operating system.  
  
 x86 ARM Cross Tools Command Prompt  
 Use this toolset to create output files for ARM machines. It runs as a 32-bit process, native on an x86 machine and under WOW64 on a 64-bit Windows operating system.  
  
 These versions of the command-line toolset are available on 64-bit platforms:  
  
 x64 x86 Cross Tools Command Prompt  
 Use this toolset to create output files for x86 machines. It runs as a native process on a 64-bit Windows operating system.  
  
 x64 Native Tools Command Prompt  
 Use this toolset to create output files for x64 machines. It runs as a native process on a 64-bit Windows operating system.  
  
 x64 ARM Cross Tools Command Prompt  
 Use this toolset to create output files for ARM machines. It runs as a native 64-bit process on a 64-bit Windows operating system.  
  
 The x86 Native Tools Command Prompt has the same effect as the Developer Command Prompt shortcut.  
  
#### To open a Developer Command Prompt window  
  
1.  In the Windows 10 **Start** menu, open **All apps** and then open the **Visual Studio** folder for your version of Visual Studio. In some earlier versions of Visual Studio, the folder is called  **Visual Studio Tools**.  
  
2.  Open the **Developer Command Prompt** shortcut for your version of Visual Studio. If you have installed the Visual C++ Build Tools edition, use the **x86 Native Tools Command Prompt**. Optionally, to run as administrator, right-click to open the shortcut menu for the Developer Command Prompt and choose **More**, **Run as Administrator**.  
  
 The Developer Command Prompt shortcut sets the environment to use the 32-bit native toolset to target x86 processors. In the same folder, there are other command prompt shortcuts that specify different native platforms and cross-compiler targets. For example, choose the **x64 Cross Tools Command Prompt** to use the 32-bit native toolset to target x64 processors. Choose the **ARM Cross Tools Command Prompt** to use the 32-bit native toolset to target ARM processors. Choose the **x64 Native Tools Command Prompt** to use the 64-bit native toolset to target x64 processors.  
  
## Using vcvarsall.bat in a Command Prompt window  
 By running vcvarsall.bat in a plain Command Prompt window, you can set environment variables to configure the command line for native 32-bit or 64-bit compilation, or for cross-compilation to x86, x64, or ARM processors. If no arguments are provided, vcvarsall.bat configures the environment variables for using the 32-bit native compiler for x86 targets. However, you can use it to configure any of the compilers. If you specify a compiler configuration that is not installed or is not available on your build computer architecture, a message is displayed. The following table shows the supported arguments.  
  
|Vcvarsall.bat argument|Compiler|Build-computer architecture|Build output architecture|  
|----------------------------|--------------|----------------------------------|-------------------------------|  
|x86|x86 32-bit native|x86, x64|x86|  
|x86_amd64|x64 on x86 cross|x86, x64|x64|  
|x86_arm|ARM on x86 cross|x86, x64|ARM|  
|amd64|x64 64-bit native|x64|x64|  
|amd64_x86|x86 on x64 cross|x64|x86|  
|amd64_arm|ARM on x64 cross|x64|ARM|  
  
 The following steps show how to configure a Command Prompt to use the 32-bit native toolset to target x86 platforms.  
  
#### To run vcvarsall.bat  
  
1.  At the command prompt, change to the Visual C++ installation directory. (The location depends on the system and the Visual Studio installation, but a typical location is C:\Program Files (x86)\Microsoft Visual Studio *version*\VC\\.) For example, enter:  
  
     **cd "Program Files (x86)Microsoft Visual Studio 14.0VC"**  
  
2.  To configure this Command Prompt window for 32-bit x86 command-line builds, at the command prompt, enter:  
  
     `vcvarsall x86`  
  
 The command file sets the required environment variables for the paths to the build tools, libraries, and headers. You can now use this command prompt window to run the command-line compiler and tools.  
  
 Visual Studio also provides vcvars32.bat to set up a command-line environment. The vcvars32.bat file is found in the bin directory under the VC installation directory. It's limited to setting the appropriate environment variables to enable 32-bit x86 command-line builds. It's the equivalent of the `vcvarsall x86` command.  
  
 If you are using [DEVENV](../Topic/Devenv%20Command%20Line%20Switches.md) for command-line builds, the environment set by vcvarsall.bat or vcvars32.bat does not affect your builds, unless you also specify the **/useenv** option.  
  
> [!CAUTION]
>  The vcvarsall.bat file can vary from computer to computer. Do not replace a missing or damaged vcvarsall.bat file by using a file from another computer. Rerun Visual Studio Setup to replace the missing file.  
>   
>  The vcvarsall.bat file also varies from version to version. If the current version of Visual C++ is installed on a computer that also has an earlier version of Visual C++, do not run vcvarsall.bat or vcvars32.bat from the different versions in the same Command Prompt window.  
  
## See Also  
 [Building on the Command Line](../VS_visualcpp/Building-on-the-Command-Line.md)   
 [Linking](../VS_visualcpp/Linking.md)   
 [Linker Options](../VS_visualcpp/Linker-Options.md)   
 [Compiling a C/C++ Program](../VS_visualcpp/Compiling-a-C-C---Program.md)   
 [Compiler Options](../VS_visualcpp/Compiler-Options.md)