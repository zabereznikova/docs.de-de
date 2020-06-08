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
ms.openlocfilehash: 496627d3b77b0382ae7d15c8225a6fbd41f1db73
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403121"
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="89128-102">Beispiele für Kompilierungsbefehlszeilen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89128-102">Sample compilation command lines (Visual Basic)</span></span>

<span data-ttu-id="89128-103">Alternativ zum Kompilieren von Visual Basic-Programmen in Visual Studio können Sie diese über die Befehlszeile kompilieren, um ausführbare Dateien (.exe) oder DLL-Dateien (.dll) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89128-103">As an alternative to compiling Visual Basic programs from within Visual Studio, you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>

<span data-ttu-id="89128-104">Der Visual Basic-Befehlszeilencompiler unterstützt sämtliche Optionen, die Eingabe- und Ausgabedateien, Assemblys sowie Debug- und Präprozessoroptionen steuern.</span><span class="sxs-lookup"><span data-stu-id="89128-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="89128-105">Jede Option ist in zwei austauschbaren Formaten verfügbar: `-option` und `/option`.</span><span class="sxs-lookup"><span data-stu-id="89128-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="89128-106">In dieser Dokumentation wird nur das `-option`-Format dargestellt.</span><span class="sxs-lookup"><span data-stu-id="89128-106">This documentation shows only the `-option` form.</span></span>

<span data-ttu-id="89128-107">In der folgenden Tabelle sind einige Beispielbefehlszeilen aufgelistet, die Sie anpassen können.</span><span class="sxs-lookup"><span data-stu-id="89128-107">The following table lists some sample command lines you can modify for your own use.</span></span>

|<span data-ttu-id="89128-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89128-108">To</span></span>|<span data-ttu-id="89128-109">Verwendung</span><span class="sxs-lookup"><span data-stu-id="89128-109">Use</span></span>|
|--------|---------|
|<span data-ttu-id="89128-110">Kompiliert „File.vb“ und erstellt „File.exe“</span><span class="sxs-lookup"><span data-stu-id="89128-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|<span data-ttu-id="89128-111">Kompiliert „File.vb“ und erstellt „File.dll“</span><span class="sxs-lookup"><span data-stu-id="89128-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|
|<span data-ttu-id="89128-112">Kompiliert „File.vb“ und erstellt „My.exe“</span><span class="sxs-lookup"><span data-stu-id="89128-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|
|<span data-ttu-id="89128-113">Kompiliert „File.vb“ und erstellt eine Bibliothek und eine Verweisassembly namens „File.dll“</span><span class="sxs-lookup"><span data-stu-id="89128-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="89128-114">Kompiliert alle Visual Basic-Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen dem definierten `DEBUG`-Symbol und erstellt „File2.exe“</span><span class="sxs-lookup"><span data-stu-id="89128-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|<span data-ttu-id="89128-115">Kompiliert alle Visual Basic-Dateien im aktuellen Verzeichnis und erstellt eine Debugversion von „File2.dll“, ohne das Logo oder Warnungen anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="89128-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|<span data-ttu-id="89128-116">Kompiliert alle C#-Dateien im aktuellen Verzeichnis zu „Something.dll“</span><span class="sxs-lookup"><span data-stu-id="89128-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> <span data-ttu-id="89128-117">Wenn Sie ein Projekt mit der Visual Studio-IDE erstellen, können Sie Informationen zum zugeordneten Befehl **vbc** und dessen Compileroptionen im Ausgabefenster anzeigen.</span><span class="sxs-lookup"><span data-stu-id="89128-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="89128-118">Navigieren Sie hierzu zu [Optionen > Projekte und Projektmappen > Kompilieren und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie die **Ausführlichkeit der MSBuild-Projektbuildausgabe** auf **Normal** oder höher fest.</span><span class="sxs-lookup"><span data-stu-id="89128-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>

## <a name="see-also"></a><span data-ttu-id="89128-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89128-119">See also</span></span>

- [<span data-ttu-id="89128-120">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="89128-120">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="89128-121">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="89128-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
