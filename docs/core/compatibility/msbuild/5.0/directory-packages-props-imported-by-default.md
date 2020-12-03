---
title: 'Breaking Change: Directory.Packages.props-Dateien werden standardmäßig importiert'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den NuGet-Dateien des Typs „.props“ automatisch eine Datei namens „Directory.Packages.props“ importieren, wenn sie im Projektordner gefunden wird.
ms.date: 09/17/2020
ms.openlocfilehash: ee8a2999b801e81750d96a0bc985e3c8169224a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759406"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="7c7d1-103">Directory.Packages.props-Dateien werden standardmäßig importiert</span><span class="sxs-lookup"><span data-stu-id="7c7d1-103">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="7c7d1-104">NuGet-Dateien des Typs *.props* importieren automatisch eine Datei namens *Directory.Packages.props*, wenn sie im Projektordner oder einem seiner Vorgänger gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-104">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7c7d1-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="7c7d1-105">Version introduced</span></span>

<span data-ttu-id="7c7d1-106">5.0</span><span class="sxs-lookup"><span data-stu-id="7c7d1-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="7c7d1-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="7c7d1-107">Change description</span></span>

<span data-ttu-id="7c7d1-108">In früheren .NET-Versionen konnte eine Datei mit dem Namen *Directory.Packages.props* in Ihrer Projektdatei enthalten sein, die zur Buildzeit nicht automatisch von der NuGet-Datei *.props* importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-108">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="7c7d1-109">Ab .NET 5.0 wird eine solche Datei *automatisch* importiert, wenn sie im Projektordner oder einem seiner Vorgänger vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-109">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="7c7d1-110">Wenn Sie eine Datei mit diesem Namen in Ihrem Projektordner haben, könnte dieser automatische Import das Verhalten des Builds ändern.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-110">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="7c7d1-111">Die Datei wird z. B. importiert, was vorher aber nicht der Fall war, oder die Reihenfolge, in der sie importiert wird, könnte sich ändern, wenn Sie sie gezielt importieren.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-111">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7c7d1-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="7c7d1-112">Reason for change</span></span>

<span data-ttu-id="7c7d1-113">Diese Änderung wurde vorgenommen, um eine [zentrale Paketversionsverwaltung](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) für NuGet zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-113">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7c7d1-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="7c7d1-114">Recommended action</span></span>

<span data-ttu-id="7c7d1-115">Benennen Sie die vorhandene Datei *Directory.Packages.props* um, wenn sie nicht automatisch importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c7d1-115">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7c7d1-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7c7d1-116">Affected APIs</span></span>

<span data-ttu-id="7c7d1-117">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="7c7d1-117">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
