---
title: Erstellen von der Befehlszeile aus (Visual Basic) | Microsoft-Dokumentation
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
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers, invoking from command line
- command-line builds
- compiling source code
- command-line compilers, Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
caps.latest.revision: 13
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
ms.openlocfilehash: e7550a4a54637ea5ef425a1cb7ae02abd07808a8
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="b9064-102">Erstellen von der Befehlszeile aus (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9064-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="b9064-103">Ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Projekt besteht aus einem oder mehreren separaten Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="b9064-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project is made up of one or more separate source files.</span></span> <span data-ttu-id="b9064-104">Bei der Kompilierung genannt, werden diese Dateien in einem Paket zusammengefasst – einer einzelnen ausführbaren Datei, die als eine Anwendung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9064-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b9064-105">Stellt einen Befehlszeilencompiler als Alternative zum Kompilieren von Programmen in der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] integrierten Entwicklungsumgebung (IDE).</span><span class="sxs-lookup"><span data-stu-id="b9064-105"> provides a command-line compiler as an alternative to compiling programs from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] integrated development environment (IDE).</span></span> <span data-ttu-id="b9064-106">Der Befehlszeilencompiler eignet sich für Situationen, in dem Sie den vollständigen Satz von Funktionen in der IDE nicht benötigen, z. B. Wenn Sie mithilfe von oder für Computer mit begrenztem Arbeitsspeicher oder ein Speicherplatz schreiben.</span><span class="sxs-lookup"><span data-stu-id="b9064-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
 <span data-ttu-id="b9064-107">Beim Kompilieren von der Befehlszeile aus müssen Sie explizit verweisen, auf die Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Laufzeitbibliothek über die `/reference` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="b9064-107">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
 <span data-ttu-id="b9064-108">Zum Kompilieren von Quelldateien in der [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] IDE, wählen Sie die **erstellen** Befehl die **erstellen** im Menü.</span><span class="sxs-lookup"><span data-stu-id="b9064-108">To compile source files from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="b9064-109">Wenn Sie Dateien mithilfe von Visual Studio-IDE erstellen, können Sie anzeigen, Informationen zum zugehörigen **Vbc** Befehl und Schaltern im Ausgabefenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9064-109">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="b9064-110">Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder eine höhere Stufe der Ausführlichkeit.</span><span class="sxs-lookup"><span data-stu-id="b9064-110">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="b9064-111">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span><span class="sxs-lookup"><span data-stu-id="b9064-111">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
 <span data-ttu-id="b9064-112">Sie können Projektdateien (.vbproj) in einer Befehlszeile kompilieren, mithilfe von MSBuild.</span><span class="sxs-lookup"><span data-stu-id="b9064-112">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="b9064-113">Weitere Informationen finden Sie unter [-Befehlszeilenreferenz](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) und [Exemplarische Vorgehensweise: Verwenden von MSBuild](http://msdn.microsoft.com/library/b8a8b866-bb07-4abf-b9ec-0b40d281c310).</span><span class="sxs-lookup"><span data-stu-id="b9064-113">For more information, see [Command-Line Reference](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](http://msdn.microsoft.com/library/b8a8b866-bb07-4abf-b9ec-0b40d281c310).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b9064-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b9064-114">In This Section</span></span>  
 [<span data-ttu-id="b9064-115">Gewusst wie: Aufrufen des Befehlszeilencompilers</span><span class="sxs-lookup"><span data-stu-id="b9064-115">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="b9064-116">Beschreibt das Aufrufen des Befehlszeilencompilers auf MS-DOS oder von einem bestimmten Unterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b9064-116">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="b9064-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b9064-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="b9064-118">Enthält eine Liste mit Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.</span><span class="sxs-lookup"><span data-stu-id="b9064-118">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b9064-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b9064-119">Related Sections</span></span>  
 [<span data-ttu-id="b9064-120">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b9064-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="b9064-121">Enthält eine Liste der Compileroptionen alphabetisch oder nach ihrem Zweck geordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b9064-121">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="b9064-122">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="b9064-122">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="b9064-123">Beschreibt, wie bestimmte Codeabschnitte kompiliert.</span><span class="sxs-lookup"><span data-stu-id="b9064-123">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="b9064-124">Erstellen und Bereinigen von Projekten und Projektmappen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b9064-124">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](https://docs.microsoft.com/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="b9064-125">Beschreibt das Organisieren, was in verschiedenen Builds eingeschlossen, Projekteigenschaften auswählen und sicherstellen, dass Projekte in der richtigen Reihenfolge erstellen.</span><span class="sxs-lookup"><span data-stu-id="b9064-125">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
