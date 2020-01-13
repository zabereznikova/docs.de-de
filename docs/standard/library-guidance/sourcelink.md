---
title: SourceLink und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Verwenden von SourceLink zur Verbesserung des Debuggens für .NET-Bibliotheken.
ms.date: 01/15/2019
ms.openlocfilehash: 0ebc7601f1ad92b0fc6ab4c7599b010cb42feb5d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706438"
---
# <a name="source-link"></a><span data-ttu-id="d1fc7-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="d1fc7-103">Source Link</span></span>

<span data-ttu-id="d1fc7-104">SourceLink ist eine Technologie, mit der Entwickler Quellcode aus .NET-Assemblys über NuGet debuggen können.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-104">Source Link is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="d1fc7-105">SourceLink wird beim Erstellen des NuGet-Pakets ausgeführt und bettet Metadaten der Quellcodeverwaltung in Assemblys und das Paket ein.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-105">Source Link executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="d1fc7-106">Entwickler, die das Paket herunterladen und SourceLink in Visual Studio aktiviert haben, können den Quellcode schrittweise ausführen.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-106">Developers who download the package and have Source Link enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="d1fc7-107">SourceLink bietet Metadaten zur Quellcodeverwaltung, um das Debuggen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-107">Source Link provides source control metadata to create a great debugging experience.</span></span>

## <a name="source-link-demo"></a><span data-ttu-id="d1fc7-108">SourceLink-Demo</span><span class="sxs-lookup"><span data-stu-id="d1fc7-108">Source Link demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a><span data-ttu-id="d1fc7-109">Verwenden von SourceLink</span><span class="sxs-lookup"><span data-stu-id="d1fc7-109">Using Source Link</span></span>

<span data-ttu-id="d1fc7-110">Anweisungen zum Verwenden von SourceLink finden Sie im GitHub-Repository [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="d1fc7-110">Instructions for using Source Link can be found on the [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="d1fc7-111">Sie können mit dem [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) bestätigen, dass die SourceLink-Metadaten erfolgreich in das Paket eingebettet wurden.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the Source Link metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="d1fc7-112">Überprüfen Sie, ob die `Repository`-Metadaten über eine Commit-ID verfügen, und ob sich PDB-Dateien in der jeweiligen DLL-Zieldatei befinden.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-112">Check the `Repository` metadata is present with a commit identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="d1fc7-113">![Quellenlink im NuGet-Paket-Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Quellenlink im NuGet-Paket-Explorer")</span><span class="sxs-lookup"><span data-stu-id="d1fc7-113">![Source Link in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Source Link in NuGet Package Explorer")</span></span>

<span data-ttu-id="d1fc7-114">**✔️ ERWÄGEN SIE**, mit SourceLink ggf. Metadaten der Quellcodeverwaltung Ihren Assemblys und NuGet-Paketen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-114">**✔️ CONSIDER** using Source Link to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="d1fc7-115">Sie können für Entwickler den Debugvorgang weiter verbessern, indem Sie Ihren Typen Debuggerattribute hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
>
> * <span data-ttu-id="d1fc7-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> kann anpassen, wie eine Klasse oder ein Feld in den Variablenfenstern des Debuggers angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="d1fc7-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> weist den Debugger an, schrittweise durch den Code zu laufen, anstatt ihn schrittweise auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="d1fc7-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> bestimmt, ob und wie ein Member in Debuggervariablenfenstern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="d1fc7-119">**✔️ ERWÄGEN SIE** das Veröffentlichen von Symboldateien (`*.pdb`).</span><span class="sxs-lookup"><span data-stu-id="d1fc7-119">**✔️ CONSIDER** publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="d1fc7-120">Für das beste Debugergebnis sollte Ihre Bibliothek sowohl Symboldateien veröffentlichen als auch SourceLink verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1fc7-120">For the best debugging experience your library should publish symbol files as well as use Source Link.</span></span> <span data-ttu-id="d1fc7-121">Weitere Informationen zu Symboldateien und Symbolpaketen finden Sie unter [Symbolpakete](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="d1fc7-121">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d1fc7-122">[Zurück](dependencies.md)
>[Weiter](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="d1fc7-122">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
