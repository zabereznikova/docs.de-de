---
title: Beispiele für Kompilierungsbefehlszeilen (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b0f1fc1d269801efdbf2e89d10679dc8159851f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="b304e-102">Beispiel für Kompilierungsbefehlszeilen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b304e-102">Sample compilation command lines (Visual Basic)</span></span>
<span data-ttu-id="b304e-103">Als Alternative zum Kompilieren von Visual Basic-Programmen in Visual Studio können Sie über die Befehlszeile, um ausführbare Dateien (.exe) oder Dynamic Link Library (DLL) Dateien kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b304e-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="b304e-104">Die Visual Basic-Befehlszeilencompiler unterstützt einen vollständigen Satz von Optionen, die Steuerung von Eingabe- und Ausgabedateien, Assemblys und Debug und Präprozessor Optionen.</span><span class="sxs-lookup"><span data-stu-id="b304e-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="b304e-105">Jede Option steht in zwei austauschbar Formen: `-option` und `/option`.</span><span class="sxs-lookup"><span data-stu-id="b304e-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="b304e-106">Diese Dokumentation zeigt nur die `-option` Form.</span><span class="sxs-lookup"><span data-stu-id="b304e-106">This documentation shows only the `-option` form.</span></span>  
  
 <span data-ttu-id="b304e-107">Die folgende Tabelle enthält einige Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.</span><span class="sxs-lookup"><span data-stu-id="b304e-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="b304e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b304e-108">To</span></span>|<span data-ttu-id="b304e-109">Mit</span><span class="sxs-lookup"><span data-stu-id="b304e-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="b304e-110">Kompilieren Sie "File.vb" verwenden und Erstellen von File.exe</span><span class="sxs-lookup"><span data-stu-id="b304e-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="b304e-111">Kompilieren Sie "File.vb" verwenden, und Erstellen von File.dll.</span><span class="sxs-lookup"><span data-stu-id="b304e-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|  
|<span data-ttu-id="b304e-112">Kompilieren Sie "File.vb" verwenden und Erstellen von My.exe</span><span class="sxs-lookup"><span data-stu-id="b304e-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|  
|<span data-ttu-id="b304e-113">Kompilieren Sie "File.vb" verwenden, und erstellen Sie eine Bibliothek und eine Verweisassembly mit dem Namen "Datei.dll"</span><span class="sxs-lookup"><span data-stu-id="b304e-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="b304e-114">Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen auf und die `DEBUG` Symbol definiert ist, erzeugt File2.exe</span><span class="sxs-lookup"><span data-stu-id="b304e-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|<span data-ttu-id="b304e-115">Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis, wodurch eine Debugversion von File2.dll ohne das Logo oder Warnungen</span><span class="sxs-lookup"><span data-stu-id="b304e-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|<span data-ttu-id="b304e-116">Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis zu Something.dll</span><span class="sxs-lookup"><span data-stu-id="b304e-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  <span data-ttu-id="b304e-117">Beim Erstellen eines Projekts mit Visual Studio-IDE können Sie Informationen zum zugehörigen anzeigen **Vbc** mit seiner Compileroptionen im Fenster "Ausgabe".</span><span class="sxs-lookup"><span data-stu-id="b304e-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="b304e-118">Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder ein höheres Maß an Ausführlichkeit.</span><span class="sxs-lookup"><span data-stu-id="b304e-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="b304e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b304e-119">See Also</span></span>  
 [<span data-ttu-id="b304e-120">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b304e-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b304e-121">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="b304e-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
