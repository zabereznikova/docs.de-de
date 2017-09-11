---
title: "Beispiele für Kompilierungsbefehlszeilen (Visual Basic) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e58006c05f498ec1a9dbf5194fbc9bcdd281ab63
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="caa5b-102">Beispiele für Kompilierungsbefehlszeilen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="caa5b-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="caa5b-103">Als Alternative zum Kompilieren von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Programmen in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], können Sie die Kompilierung von der Befehlszeile aus, ausführbare Dateien (.exe) oder Dynamic Link Library (DLL) Dateien.</span><span class="sxs-lookup"><span data-stu-id="caa5b-103">As an alternative to compiling [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programs from within [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="caa5b-104">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Befehlszeilencompiler unterstützt einen vollständigen Satz von Optionen zur Steuerung von Eingabe-und Ausgabedateien, Assemblys und Debug und Präprozessor Optionen.</span><span class="sxs-lookup"><span data-stu-id="caa5b-104">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="caa5b-105">Jede Option liegt in zwei austauschbaren Varianten: `-``option` und `/``option`.</span><span class="sxs-lookup"><span data-stu-id="caa5b-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="caa5b-106">In dieser Dokumentation wird nur die `/``option` Form.</span><span class="sxs-lookup"><span data-stu-id="caa5b-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="caa5b-107">Die folgende Tabelle enthält einige Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.</span><span class="sxs-lookup"><span data-stu-id="caa5b-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="caa5b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="caa5b-108">To</span></span>|<span data-ttu-id="caa5b-109">Verwendung</span><span class="sxs-lookup"><span data-stu-id="caa5b-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="caa5b-110">VB-Datei zu kompilieren und Erstellen von File.exe</span><span class="sxs-lookup"><span data-stu-id="caa5b-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="caa5b-111">VB-Datei zu kompilieren und Erstellen von File.dll.</span><span class="sxs-lookup"><span data-stu-id="caa5b-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="caa5b-112">VB-Datei zu kompilieren und Erstellen von My.exe</span><span class="sxs-lookup"><span data-stu-id="caa5b-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="caa5b-113">Kompilieren Sie alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen und `DEBUG` -Symbol File2.exe erzeugen</span><span class="sxs-lookup"><span data-stu-id="caa5b-113">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="caa5b-114">Kompilieren Sie alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien im aktuellen Verzeichnis befindet, erzeugen eine Debugversion von File2.dll erstellt wird, ohne das Logo oder Warnungen</span><span class="sxs-lookup"><span data-stu-id="caa5b-114">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="caa5b-115">Kompilieren Sie alle [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Dateien im aktuellen Verzeichnis zu Something.dll</span><span class="sxs-lookup"><span data-stu-id="caa5b-115">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="caa5b-116">Beim Kompilieren von der Befehlszeile aus müssen Sie explizit verweisen, auf die Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Laufzeitbibliothek über die `/reference` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="caa5b-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="caa5b-117">Wenn Sie ein Projekt mithilfe von Visual Studio-IDE erstellen, können Sie Informationen zum zugehörigen anzeigen **Vbc** Befehl seine Compileroptionen im Ausgabefenster.</span><span class="sxs-lookup"><span data-stu-id="caa5b-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="caa5b-118">Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder eine höhere Stufe der Ausführlichkeit.</span><span class="sxs-lookup"><span data-stu-id="caa5b-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="caa5b-119">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="caa5b-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa5b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="caa5b-120">See Also</span></span>  
 <span data-ttu-id="caa5b-121">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="caa5b-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="caa5b-122"> [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="caa5b-122"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
