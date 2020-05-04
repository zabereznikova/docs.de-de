---
title: Erstellen von der Befehlszeile aus
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
ms.openlocfilehash: c7219c0497bb87f0cc44f27229eaf25f9b3eebce
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344792"
---
# <a name="building-from-the-command-line-visual-basic"></a><span data-ttu-id="bce41-102">Erstellen von der Befehlszeile aus (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bce41-102">Building from the Command Line (Visual Basic)</span></span>

<span data-ttu-id="bce41-103">Ein Visual Basic-Projekt besteht aus einer oder mehreren separaten Quelldateien.</span><span class="sxs-lookup"><span data-stu-id="bce41-103">A Visual Basic project is made up of one or more separate source files.</span></span> <span data-ttu-id="bce41-104">Während des Prozesses, der als Kompilierung bezeichnet wird, werden diese Dateien in einem Paket zusammengefasst: einer einzelnen ausführbaren Datei, die als Anwendung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bce41-104">During the process known as compilation, these files are brought together into one package—a single executable file that can be run as an application.</span></span>

<span data-ttu-id="bce41-105">Visual Basic bietet mit dem Befehlszeilencompiler eine Alternative zum Kompilieren von Programmen in der integrierten Entwicklungsumgebung (IDE) von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bce41-105">Visual Basic provides a command-line compiler as an alternative to compiling programs from within the Visual Studio integrated development environment (IDE).</span></span> <span data-ttu-id="bce41-106">Der Befehlszeilencompiler ist für Situationen konzipiert, in denen Sie nicht alle Features der IDE benötigen – beispielsweise wenn Sie Programme für Computer mit eingeschränktem Systemarbeitsspeicher oder -speicher verwenden oder schreiben.</span><span class="sxs-lookup"><span data-stu-id="bce41-106">The command-line compiler is designed for situations in which you do not require the full set of features in the IDE—for example, when you are using or writing for computers with limited system memory or storage space.</span></span>

<span data-ttu-id="bce41-107">Wenn Sie Quelldateien in der Visual Studio-IDE kompilieren möchten, klicken Sie im Menü **Erstellen** auf **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="bce41-107">To compile source files from within the Visual Studio IDE, choose the **Build** command from the **Build** menu.</span></span>

> [!TIP]
> <span data-ttu-id="bce41-108">Wenn Sie Projektdateien mit der Visual Studio-IDE erstellen, können Sie Informationen zum zugeordneten Befehl **vbc** und dessen Parameter im Ausgabefenster anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bce41-108">When you build project files by using the Visual Studio IDE, you can display information about the associated **vbc** command and its switches in the output window.</span></span> <span data-ttu-id="bce41-109">Navigieren Sie hierzu zu [Optionen > Projekte und Projektmappen > Kompilieren und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie die **Ausführlichkeit der MSBuild-Projektbuildausgabe** auf **Normal** oder höher fest.</span><span class="sxs-lookup"><span data-stu-id="bce41-109">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="bce41-110">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen, Speichern und Konfigurieren von Buildprotokolldateien](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span><span class="sxs-lookup"><span data-stu-id="bce41-110">For more information, see [How to: View, Save, and Configure Build Log Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files).</span></span>

<span data-ttu-id="bce41-111">Sie können Projektdateien (.vbproj) mithilfe von MSBuild in einer Eingabeaufforderung kompilieren.</span><span class="sxs-lookup"><span data-stu-id="bce41-111">You can compile project (.vbproj) files at a command prompt by using MSBuild.</span></span> <span data-ttu-id="bce41-112">Weitere Informationen finden Sie unter [Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference) und [Exemplarische Vorgehensweise: Verwenden von MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span><span class="sxs-lookup"><span data-stu-id="bce41-112">For more information, see [Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) and [Walkthrough: Using MSBuild](/visualstudio/msbuild/walkthrough-using-msbuild).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bce41-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bce41-113">In This Section</span></span>

<span data-ttu-id="bce41-114">[How to: Aufrufen des Befehlszeilencompilers](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span><span class="sxs-lookup"><span data-stu-id="bce41-114">[How to: Invoke the Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/how-to-invoke-the-command-line-compiler.md) </span></span>\
<span data-ttu-id="bce41-115">Beschreibt, wie der Befehlszeilencompiler in der MS-DOS-Eingabeaufforderung oder über ein bestimmtes Unterverzeichnis aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bce41-115">Describes how to invoke the command-line compiler at the MS-DOS prompt or from a specific subdirectory.</span></span>

<span data-ttu-id="bce41-116">[Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="bce41-116">[Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>\
<span data-ttu-id="bce41-117">Enthält eine Liste mit Beispielbefehlszeilen, die Sie nach Belieben anpassen können.</span><span class="sxs-lookup"><span data-stu-id="bce41-117">Provides a list of sample command lines that you can modify for your own use.</span></span>

## <a name="related-sections"></a><span data-ttu-id="bce41-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="bce41-118">Related Sections</span></span>

<span data-ttu-id="bce41-119">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="bce41-119">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>\
<span data-ttu-id="bce41-120">Enthält Listen mit Compileroptionen, die alphabetisch oder nach Zweck angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bce41-120">Provides lists of compiler options, organized alphabetically or by purpose.</span></span>

<span data-ttu-id="bce41-121">[Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="bce41-121">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>\
<span data-ttu-id="bce41-122">Beschreibt, wie bestimmte Codeabschnitte kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="bce41-122">Describes how to compile particular sections of code.</span></span>

<span data-ttu-id="bce41-123">[Erstellen und Bereinigen von Projekten und Projektmappen in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="bce41-123">[Building and Cleaning Projects and Solutions in Visual Studio](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio) </span></span>\
<span data-ttu-id="bce41-124">Beschreibt, wie Sie die in verschiedenen Builds enthaltenen Elemente organisieren, Projekteigenschaften auswählen und sicherstellen, dass Projekte in der richtigen Reihenfolge erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bce41-124">Describes how to organize what will be included in different builds, choose project properties, and ensure that projects build in the correct order.</span></span>
