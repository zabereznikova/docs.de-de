---
title: SourceLink und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Verwenden von SourceLink zur Verbesserung des Debuggens für .NET-Bibliotheken.
ms.date: 01/15/2019
ms.openlocfilehash: 0261019087bce8e9d088a90c5e36bdd0b22f556b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212424"
---
# <a name="source-link"></a><span data-ttu-id="353f0-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="353f0-103">Source Link</span></span>

<span data-ttu-id="353f0-104">SourceLink ist eine Technologie, mit der Entwickler Quellcode aus .NET-Assemblys über NuGet debuggen können.</span><span class="sxs-lookup"><span data-stu-id="353f0-104">Source Link is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="353f0-105">SourceLink wird beim Erstellen des NuGet-Pakets ausgeführt und bettet Metadaten der Quellcodeverwaltung in Assemblys und das Paket ein.</span><span class="sxs-lookup"><span data-stu-id="353f0-105">Source Link executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="353f0-106">Entwickler, die das Paket herunterladen und SourceLink in Visual Studio aktiviert haben, können den Quellcode schrittweise ausführen.</span><span class="sxs-lookup"><span data-stu-id="353f0-106">Developers who download the package and have Source Link enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="353f0-107">SourceLink bietet Metadaten zur Quellcodeverwaltung, um das Debuggen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="353f0-107">Source Link provides source control metadata to create a great debugging experience.</span></span>

## <a name="source-link-demo"></a><span data-ttu-id="353f0-108">SourceLink-Demo</span><span class="sxs-lookup"><span data-stu-id="353f0-108">Source Link demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a><span data-ttu-id="353f0-109">Verwenden von SourceLink</span><span class="sxs-lookup"><span data-stu-id="353f0-109">Using Source Link</span></span>

<span data-ttu-id="353f0-110">Anweisungen zum Verwenden von SourceLink finden Sie im GitHub-Repository [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="353f0-110">Instructions for using Source Link can be found on the [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="353f0-111">Sie können mit dem [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) bestätigen, dass die SourceLink-Metadaten erfolgreich in das Paket eingebettet wurden.</span><span class="sxs-lookup"><span data-stu-id="353f0-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the Source Link metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="353f0-112">Überprüfen Sie, ob die `Repository`-Metadaten über eine Commit-ID verfügen, und ob sich PDB-Dateien in der jeweiligen DLL-Zieldatei befinden.</span><span class="sxs-lookup"><span data-stu-id="353f0-112">Check the `Repository` metadata is present with a commit identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="353f0-113">![Quellenlink im NuGet-Paket-Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Quellenlink im NuGet-Paket-Explorer")</span><span class="sxs-lookup"><span data-stu-id="353f0-113">![Source Link in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Source Link in NuGet Package Explorer")</span></span>

<span data-ttu-id="353f0-114">✔️ Erwägen Sie, Ihren Assemblys und NuGet-Paketen gegebenenfalls mithilfe von Source Link Metadaten der Quellcodeverwaltung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="353f0-114">✔️ CONSIDER using Source Link to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="353f0-115">Sie können für Entwickler den Debugvorgang weiter verbessern, indem Sie Ihren Typen Debuggerattribute hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="353f0-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
>
> * <span data-ttu-id="353f0-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> kann anpassen, wie eine Klasse oder ein Feld in den Variablenfenstern des Debuggers angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="353f0-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="353f0-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> weist den Debugger an, schrittweise durch den Code zu laufen, anstatt ihn schrittweise auszuführen.</span><span class="sxs-lookup"><span data-stu-id="353f0-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="353f0-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> bestimmt, ob und wie ein Member in Debuggervariablenfenstern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="353f0-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="353f0-119">✔️ Erwägen Sie, Symboldateien zu veröffentlichen (`*.pdb`).</span><span class="sxs-lookup"><span data-stu-id="353f0-119">✔️ CONSIDER publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="353f0-120">Für das beste Debugergebnis sollte Ihre Bibliothek sowohl Symboldateien veröffentlichen als auch SourceLink verwenden.</span><span class="sxs-lookup"><span data-stu-id="353f0-120">For the best debugging experience your library should publish symbol files as well as use Source Link.</span></span> <span data-ttu-id="353f0-121">Weitere Informationen zu Symboldateien und Symbolpaketen finden Sie unter [Symbolpakete](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="353f0-121">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

<span data-ttu-id="353f0-122">✔️ ERWÄGEN SIE, deterministische Builds zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="353f0-122">✔️ CONSIDER enabling deterministic builds.</span></span>

> <span data-ttu-id="353f0-123">Deterministische Builds ermöglichen die Überprüfung, ob die resultierende Binärdatei aus der angegebenen Quelle erstellt wurde, und die Nachverfolgbarkeit.</span><span class="sxs-lookup"><span data-stu-id="353f0-123">Deterministic builds enable verification that the resulting binary was built from the specified source and provide traceability.</span></span> <span data-ttu-id="353f0-124">Weitere Informationen zu deterministischen Builds und Anweisungen zu deren Aktivierung finden Sie unter [Deterministic Builds](https://github.com/clairernovotny/DeterministicBuilds) (Deterministische Builds).</span><span class="sxs-lookup"><span data-stu-id="353f0-124">For more information about deterministic builds and instructions for enabling them, see [Deterministic Builds](https://github.com/clairernovotny/DeterministicBuilds).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="353f0-125">[Zurück](dependencies.md)
>[Weiter](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="353f0-125">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
