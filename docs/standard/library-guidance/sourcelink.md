---
title: SourceLink und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Verwenden von SourceLink zur Verbesserung des Debuggens für .NET-Bibliotheken.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 3bc72e158a5773b656095f9ce58b442469f91e67
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128926"
---
# <a name="sourcelink"></a><span data-ttu-id="1dd7d-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="1dd7d-103">SourceLink</span></span>

<span data-ttu-id="1dd7d-104">SourceLink ist eine Technologie, mit der Entwickler Quellcode aus .NET-Assemblys über NuGet debuggen können.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="1dd7d-105">SourceLink wird beim Erstellen des NuGet-Pakets ausgeführt und bettet Metadaten der Quellcodeverwaltung in Assemblys und das Paket ein.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="1dd7d-106">Entwickler, die das Paket herunterladen und SourceLink in Visual Studio aktiviert haben, können den Quellcode schrittweise ausführen.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="1dd7d-107">SourceLink bietet Metadaten zur Quellcodeverwaltung, um das Debuggen zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="1dd7d-108">SourceLink-Demo</span><span class="sxs-lookup"><span data-stu-id="1dd7d-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="1dd7d-109">Verwenden von SourceLink</span><span class="sxs-lookup"><span data-stu-id="1dd7d-109">Using SourceLink</span></span>

<span data-ttu-id="1dd7d-110">Anweisungen zum Verwenden von SourceLink finden Sie im GitHub-Repository [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="1dd7d-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="1dd7d-111">Sie können mit dem [NuGet-Paket-Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) bestätigen, dass die SourceLink-Metadaten erfolgreich in das Paket eingebettet wurden.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="1dd7d-112">Überprüfen Sie, ob die `Repository`-Metadaten über einen Kommentarbezeichner verfügen, und ob sich PDB-Dateien in der jeweiligen DLL-Zieldatei befinden.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="1dd7d-113">![SourceLink im NuGet-Paket-Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink im NuGet-Paket-Explorer")</span><span class="sxs-lookup"><span data-stu-id="1dd7d-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="1dd7d-114">**✔️ Fügen** Sie mit SourceLink ggf. Metadaten der Quellcodeverwaltung Ihren Assemblys und NuGet-Paketen hinzu.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="1dd7d-115">Sie können für Entwickler den Debugvorgang weiter verbessern, indem Sie Ihren Typen Debuggerattribute hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
> * <span data-ttu-id="1dd7d-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> kann anpassen, wie eine Klasse oder ein Feld in den Variablenfenstern des Debuggers angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="1dd7d-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> weist den Debugger an, schrittweise durch den Code zu laufen, anstatt ihn schrittweise auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="1dd7d-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> bestimmt, ob und wie ein Member in Debuggervariablenfenstern angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="1dd7d-119">**✔️ Betten** Sie Symboldateien (`*.pdb`) in das NuGet-Paket ein.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-119">**✔️ CONSIDER** including symbol files (`*.pdb`) in the NuGet package.</span></span>

> <span data-ttu-id="1dd7d-120">Normalerweise werden Symboldateien in einem [Symbolpaket](./nuget.md#symbol-packages) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-120">Ordinarily, you'd publish symbol files in a [symbol package](./nuget.md#symbol-packages).</span></span> <span data-ttu-id="1dd7d-121">Derzeit unterstützt der öffentliche Haupthost für Symbole nicht die portierbaren Symboldateien (`*.pdb`), die von SDK-Projekten erstellt wurden. Das bedeutet, Symbolpakete sind nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="1dd7d-121">Currently the main public host for symbol packages doesn't support the portable symbol files (`*.pdb`) created by SDK-style projects, and symbol packages aren't useful.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1dd7d-122">[Zurück](dependencies.md)
>[Weiter](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="1dd7d-122">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>