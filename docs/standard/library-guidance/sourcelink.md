---
title: Bibliotheken SourceLink und .NET
description: Empfehlungen für bewährte Methoden mit, dass die SourceLink verbessertes debugging für .NET-Bibliotheken.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49370045"
---
# <a name="sourcelink"></a><span data-ttu-id="e2a72-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="e2a72-103">SourceLink</span></span>

<span data-ttu-id="e2a72-104">SourceLink ist eine Technologie, die es ermöglicht, Debuggen von Quellcode von .NET-Assemblys aus NuGet von Entwicklern.</span><span class="sxs-lookup"><span data-stu-id="e2a72-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="e2a72-105">SourceLink ausgeführt wird, wenn das NuGet-Paket zu erstellen und Datenquellen-Steuerelement-Metadaten in Assemblys und das Paket eingebettet.</span><span class="sxs-lookup"><span data-stu-id="e2a72-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="e2a72-106">Entwickler, die das Paket herunterladen und SourceLink in Visual Studio aktiviert haben, können deren Quellcode schrittweise.</span><span class="sxs-lookup"><span data-stu-id="e2a72-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="e2a72-107">SourceLink enthält Datenquellen-Steuerelement-Metadaten um eine gute Debugleistung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2a72-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="e2a72-108">SourceLink-demo</span><span class="sxs-lookup"><span data-stu-id="e2a72-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="e2a72-109">Verwenden die SourceLink</span><span class="sxs-lookup"><span data-stu-id="e2a72-109">Using SourceLink</span></span>

<span data-ttu-id="e2a72-110">Anweisungen zur Verwendung von SourceLink finden Sie auf die [Dotnet/SourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="e2a72-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="e2a72-111">Sie können [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) zu bestätigen, dass die SourceLink-Metadaten in das Paket erfolgreich eingebettet wurde.</span><span class="sxs-lookup"><span data-stu-id="e2a72-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="e2a72-112">Überprüfen Sie die `Repository` Metadaten mit einem Kommentar Bezeichner vorhanden ist und dass PDB-Dateien sich auf die DLL-Datei des Ziels.</span><span class="sxs-lookup"><span data-stu-id="e2a72-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="e2a72-113">![SourceLink im NuGet-Paket-Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink im NuGet-Paket-Explorer")</span><span class="sxs-lookup"><span data-stu-id="e2a72-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="e2a72-114">**✔️ GGF.** mit SourceLink Quell-Steuerelement-Metadaten für Ihre Assemblys und NuGet-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="e2a72-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

<span data-ttu-id="e2a72-115">**✔️ GGF.** PDB-Dateien in das NuGet-Paket einschließen.</span><span class="sxs-lookup"><span data-stu-id="e2a72-115">**✔️ CONSIDER** including PDB files in the NuGet package.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e2a72-116">[Zurück](./dependencies.md)
[Weiter](./publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="e2a72-116">[Previous](./dependencies.md)
[Next](./publish-nuget-package.md)</span></span>
