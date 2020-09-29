---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538817"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="336a6-101">Directory.Packages.props-Dateien werden standardmäßig importiert</span><span class="sxs-lookup"><span data-stu-id="336a6-101">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="336a6-102">NuGet-Dateien des Typs *.props* importieren automatisch eine Datei namens *Directory.Packages.props*, wenn sie im Projektordner oder einem seiner Vorgänger gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="336a6-102">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="336a6-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="336a6-103">Version introduced</span></span>

<span data-ttu-id="336a6-104">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="336a6-104">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="336a6-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="336a6-105">Change description</span></span>

<span data-ttu-id="336a6-106">In früheren .NET-Versionen konnte eine Datei mit dem Namen *Directory.Packages.props* in Ihrer Projektdatei enthalten sein, die zur Buildzeit nicht automatisch von der NuGet-Datei *.props* importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="336a6-106">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="336a6-107">Ab .NET 5.0 wird eine solche Datei *automatisch* importiert, wenn sie im Projektordner oder einem seiner Vorgänger vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="336a6-107">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="336a6-108">Wenn Sie eine Datei mit diesem Namen in Ihrem Projektordner haben, könnte dieser automatische Import das Verhalten des Builds ändern.</span><span class="sxs-lookup"><span data-stu-id="336a6-108">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="336a6-109">Die Datei wird z. B. importiert, was vorher aber nicht der Fall war, oder die Reihenfolge, in der sie importiert wird, könnte sich ändern, wenn Sie sie gezielt importieren.</span><span class="sxs-lookup"><span data-stu-id="336a6-109">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="336a6-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="336a6-110">Reason for change</span></span>

<span data-ttu-id="336a6-111">Diese Änderung wurde vorgenommen, um eine [zentrale Paketversionsverwaltung](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) für NuGet zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="336a6-111">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="336a6-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="336a6-112">Recommended action</span></span>

<span data-ttu-id="336a6-113">Benennen Sie die vorhandene Datei *Directory.Packages.props* um, wenn sie nicht automatisch importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="336a6-113">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

#### <a name="category"></a><span data-ttu-id="336a6-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="336a6-114">Category</span></span>

<span data-ttu-id="336a6-115">MSBuild</span><span class="sxs-lookup"><span data-stu-id="336a6-115">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="336a6-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="336a6-116">Affected APIs</span></span>

<span data-ttu-id="336a6-117">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="336a6-117">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
