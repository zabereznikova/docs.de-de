---
title: Beispiele für Kompilierungsbefehlszeilen
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: 27a20a5a3525353ffbced729b8ac9c98b3e48fc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350855"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="5369f-102">Beispiel-Kompilierungs Befehlszeilen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5369f-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="5369f-103">Als Alternative zum Kompilieren von Visual Basic Programmen in Visual Studio können Sie über die Befehlszeile kompilieren, um ausführbare Dateien (. exe) oder DLL-Dateien (Dynamic Link Library) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5369f-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="5369f-104">Der Visual Basic-Befehlszeilen Compiler unterstützt einen kompletten Satz von Optionen, die Eingabe-und Ausgabedateien, Assemblys sowie Debug-und Präprozessoroptionen steuern.</span><span class="sxs-lookup"><span data-stu-id="5369f-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="5369f-105">Jede Option ist in zwei austauschbaren Formularen verfügbar: `-option` und `/option`.</span><span class="sxs-lookup"><span data-stu-id="5369f-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="5369f-106">In dieser Dokumentation wird nur das `-option` Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5369f-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="5369f-107">In der folgenden Tabelle sind einige Beispiel Befehlszeilen aufgelistet, die Sie für Ihre eigene Verwendung ändern können.</span><span class="sxs-lookup"><span data-stu-id="5369f-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="5369f-108">Zweck</span><span class="sxs-lookup"><span data-stu-id="5369f-108">To</span></span>|<span data-ttu-id="5369f-109">Verwendung</span><span class="sxs-lookup"><span data-stu-id="5369f-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="5369f-110">Kompilieren Sie File. vb, und erstellen Sie File. exe.</span><span class="sxs-lookup"><span data-stu-id="5369f-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="5369f-111">Kompilieren Sie File. vb, und erstellen Sie File. dll.</span><span class="sxs-lookup"><span data-stu-id="5369f-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="5369f-112">Kompilieren Sie File. vb, und erstellen Sie My. exe.</span><span class="sxs-lookup"><span data-stu-id="5369f-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="5369f-113">Kompilieren Sie File. vb, und erstellen Sie eine Bibliothek und eine Verweisassembly mit dem Namen file. dll.</span><span class="sxs-lookup"><span data-stu-id="5369f-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="5369f-114">Kompilieren Sie alle Visual Basic Dateien im aktuellen Verzeichnis mit Optimierungen für und das `DEBUG` Symbol, das file2. exe erstellt.</span><span class="sxs-lookup"><span data-stu-id="5369f-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="5369f-115">Kompilieren Sie alle Visual Basic Dateien im aktuellen Verzeichnis, und erstellen Sie eine Debugversion von file2. dll, ohne das Logo oder die Warnungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5369f-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="5369f-116">Alle Visual Basic Dateien im aktuellen Verzeichnis in ". dll" kompilieren</span><span class="sxs-lookup"><span data-stu-id="5369f-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="5369f-117">Wenn Sie ein Projekt mithilfe der Visual Studio-IDE erstellen, können Sie Informationen zum zugeordneten **vbc** -Befehl mit seinen Compileroptionen im Ausgabefenster anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5369f-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="5369f-118">Um diese Informationen anzuzeigen, öffnen Sie das [Dialog Feld Optionen, Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **Ausführlichkeit der MSBuild-Projektbuildausgabe** auf **Normal** oder eine höhere ausführlichkeits Stufe fest.</span><span class="sxs-lookup"><span data-stu-id="5369f-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="5369f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5369f-119">See also</span></span>

- [<span data-ttu-id="5369f-120">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="5369f-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5369f-121">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="5369f-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
