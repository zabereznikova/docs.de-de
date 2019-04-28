---
title: Erstellen von der Befehlszeile aus (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- builds [Visual Basic], command-line
- Visual Basic compiler, about Visual Basic compiler
- command line [Visual Basic], compilers
- command line [Visual Basic], building from
- command line [Visual Basic], builds
- compilers [Visual Basic], invoking from command line
- command-line builds
- compiling source code
- command-line compilers [Visual Basic], Visual Basic
- command line [Visual Basic], Visual Basic
ms.assetid: e61947e9-a42e-4717-a699-5f70a98cdd03
ms.openlocfilehash: 798baa90308c83e42b335635fb23a9983f5180fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61839383"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="62284-102">Erstellen von der Befehlszeile aus (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62284-102">Building from the Command Line (Visual Basic)</span></span>
<span data-ttu-id="62284-103">Visual Basic-Projekt besteht aus einem oder mehreren separaten Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="62284-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="62284-104">Während des Prozesses, der als Kompilierung bezeichnet wird, werden diese Dateien in einem Paket zusammengefasst, eine einzelne ausführbare Datei, die als eine Anwendung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="62284-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>  
  
 <span data-ttu-id="62284-105">Visual Basic bietet einen Befehlszeilencompiler als eine Alternative zum Kompilieren von Programmen in der integrierten Entwicklungsumgebung (IDE) von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="62284-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="62284-106">Der Befehlszeilencompiler dient für Situationen, in dem Sie den vollständigen Satz von Features in der IDE nicht benötigen, z. B. Wenn Sie mithilfe von oder Schreiben von für Computer mit begrenztem Arbeitsspeicher oder ein Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="62284-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>  
  
  <span data-ttu-id="62284-107">Um Quelldateien in der Visual Studio IDE kompilieren möchten, wählen Sie die **erstellen** Befehl die **erstellen** Menü.</span><span class="sxs-lookup"><span data-stu-id="62284-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="62284-108">Wenn Sie Projektdateien mithilfe von Visual Studio-IDE erstellen, können Sie anzeigen, Informationen über die zugeordnete **Vbc** Befehl und seine Schalter im Ausgabefenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62284-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="62284-109">Um diese Informationen anzuzeigen, öffnen Sie die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild Projektbuildausgabe** zu **Normal** oder ein höheres Maß an Ausführlichkeit.</span><span class="sxs-lookup"><span data-stu-id="62284-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="62284-110">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, speichern und Konfigurieren von Buildprotokolldateien](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span><span class="sxs-lookup"><span data-stu-id="62284-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>  
  
 <span data-ttu-id="62284-111">Sie können Projektdateien (VBPROJ) an einer Eingabeaufforderung kompilieren, mithilfe von MSBuild.</span><span class="sxs-lookup"><span data-stu-id="62284-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="62284-112">Weitere Informationen finden Sie unter [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) und [Exemplarische Vorgehensweise: Verwenden von MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="62284-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62284-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62284-113">In This Section</span></span>  
 [<span data-ttu-id="62284-114">Vorgehensweise: Aufrufen des Befehlszeilencompilers</span><span class="sxs-lookup"><span data-stu-id="62284-114">How to: Invoke the Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md)  
 <span data-ttu-id="62284-115">Beschreibt, wie zum Aufrufen des Befehlszeilencompilers an der MS-DOS-Eingabeaufforderung oder aus einem bestimmten Unterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="62284-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>  
  
 [<span data-ttu-id="62284-116">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="62284-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="62284-117">Enthält eine Liste der Beispiel-Befehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.</span><span class="sxs-lookup"><span data-stu-id="62284-117">Provides a list of sample command lines that you can modify for your own use.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="62284-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="62284-118">Related Sections</span></span>  
 [<span data-ttu-id="62284-119">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="62284-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 <span data-ttu-id="62284-120">Enthält eine Liste der Compileroptionen, Zweck oder alphabetisch geordnet.</span><span class="sxs-lookup"><span data-stu-id="62284-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>  
  
 [<span data-ttu-id="62284-121">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="62284-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="62284-122">Beschreibt, wie bestimmte Codeabschnitte kompiliert.</span><span class="sxs-lookup"><span data-stu-id="62284-122">Describes how to compile particular sections of code.</span></span>  
  
 [<span data-ttu-id="62284-123">Erstellen und Bereinigen von Projekten und Projektmappen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="62284-123">Building and Cleaning Projects and Solutions in Visual Studio</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="62284-124">Beschreibt, wie zum Organisieren, was in verschiedene Builds enthalten, wählen die Projekteigenschaften und stellen Sie sicher, dass Projekte in der richtigen Reihenfolge erstellt.</span><span class="sxs-lookup"><span data-stu-id="62284-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
