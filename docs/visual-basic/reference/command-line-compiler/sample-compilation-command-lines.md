---
title: Beispiele für Kompilierungsbefehlszeilen (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7c3fac318e05c5e3d6fb9dd7117cac70ead03dc
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="0db1e-102">Beispiel für Kompilierungsbefehlszeilen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0db1e-102">Sample compilation command lines (Visual Basic)</span></span>
<span data-ttu-id="0db1e-103">Als Alternative zum Kompilieren von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] innerhalb von Programmen [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], können Sie kompilieren über die Befehlszeile, um ausführbare Dateien (.exe) oder Dynamic Link Library (DLL)-Dateien zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="0db1e-103">As an alternative to compiling [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs from within [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="0db1e-104">Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Befehlszeilencompiler unterstützt einen vollständigen Satz von Optionen, die Eingabe-und Ausgabedateien, Assemblys und Debug steuern und Präprozessor.</span><span class="sxs-lookup"><span data-stu-id="0db1e-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="0db1e-105">Jede Option steht in zwei austauschbar Formen: `-option` und `/option`.</span><span class="sxs-lookup"><span data-stu-id="0db1e-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="0db1e-106">Diese Dokumentation zeigt nur die `-option` Form.</span><span class="sxs-lookup"><span data-stu-id="0db1e-106">This documentation shows only the `-option` form.</span></span>  
  
 <span data-ttu-id="0db1e-107">Die folgende Tabelle enthält einige Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.</span><span class="sxs-lookup"><span data-stu-id="0db1e-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="0db1e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0db1e-108">To</span></span>|<span data-ttu-id="0db1e-109">Mit</span><span class="sxs-lookup"><span data-stu-id="0db1e-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="0db1e-110">Kompilieren Sie "File.vb" verwenden und Erstellen von File.exe</span><span class="sxs-lookup"><span data-stu-id="0db1e-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="0db1e-111">Kompilieren Sie "File.vb" verwenden, und Erstellen von File.dll.</span><span class="sxs-lookup"><span data-stu-id="0db1e-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|  
|<span data-ttu-id="0db1e-112">Kompilieren Sie "File.vb" verwenden und Erstellen von My.exe</span><span class="sxs-lookup"><span data-stu-id="0db1e-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|  
|<span data-ttu-id="0db1e-113">Kompilieren Sie alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen und `DEBUG` Symbol definiert ist, erzeugt File2.exe</span><span class="sxs-lookup"><span data-stu-id="0db1e-113">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|<span data-ttu-id="0db1e-114">Kompilieren Sie alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien im aktuellen Verzeichnis, wodurch eine Debugversion von File2.dll ohne das Logo oder Warnungen anzeigen</span><span class="sxs-lookup"><span data-stu-id="0db1e-114">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|<span data-ttu-id="0db1e-115">Kompilieren Sie alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Dateien im aktuellen Verzeichnis zu Something.dll</span><span class="sxs-lookup"><span data-stu-id="0db1e-115">Compile all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|  
  
 <span data-ttu-id="0db1e-116">Beim Kompilieren von der Befehlszeile aus müssen Sie explizit die Microsoft verweisen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Laufzeit-Bibliothek über die `-reference` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="0db1e-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] run-time library through the `-reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="0db1e-117">Beim Erstellen eines Projekts mit Visual Studio-IDE können Sie Informationen zum zugehörigen anzeigen **Vbc** mit seiner Compileroptionen im Fenster "Ausgabe".</span><span class="sxs-lookup"><span data-stu-id="0db1e-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="0db1e-118">Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder ein höheres Maß an Ausführlichkeit.</span><span class="sxs-lookup"><span data-stu-id="0db1e-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="0db1e-119">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="0db1e-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db1e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0db1e-120">See Also</span></span>  
 [<span data-ttu-id="0db1e-121">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0db1e-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0db1e-122">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="0db1e-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
