---
ms.openlocfilehash: 49740d3b1890d72935e6e329a4f4be836ed70b25
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497384"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a><span data-ttu-id="80d90-101">Fehlender Zielframeworkmoniker führt zum Verhalten der Version 4.0</span><span class="sxs-lookup"><span data-stu-id="80d90-101">Missing Target Framework Moniker results in 4.0 behavior</span></span>

#### <a name="details"></a><span data-ttu-id="80d90-102">Details</span><span class="sxs-lookup"><span data-stu-id="80d90-102">Details</span></span>

<span data-ttu-id="80d90-103">Anwendungen, bei denen auf Assemblyebene kein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> angewendet wurde, werden automatisch mit der Semantik (den Quirks) von .NET Framework 4.0 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="80d90-103">Applications without a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> applied at the assembly level will automatically run using the semantics (quirks) of the .NET Framework 4.0.</span></span> <span data-ttu-id="80d90-104">Um eine hohe Qualität sicherzustellen, empfiehlt es sich, dass alle Binärdateien ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> als Attribut erhalten, wodurch die Version von .NET Framework angegeben wird, mit denen sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="80d90-104">To ensure high quality, it is recommended that all binaries be explicitly attributed with a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> indicating the version of the .NET Framework they were built with.</span></span> <span data-ttu-id="80d90-105">Beachten Sie, dass die Verwendung eines Zielframeworkmonikers in einer Projektdatei dazu führt, dass MSBuild automatisch ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> anwendet.</span><span class="sxs-lookup"><span data-stu-id="80d90-105">Note that using a target framework moniker in a project file will cause MSBuild to automatically apply a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80d90-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="80d90-106">Suggestion</span></span>

<span data-ttu-id="80d90-107">Es sollte ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> bereitgestellt werden, entweder durch direktes Hinzufügen des Attributs zur Assembly oder durch Angeben eines Zielframeworks in der [Projektdatei oder über die Visual Studio-GUI für Projekteigenschaften](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span><span class="sxs-lookup"><span data-stu-id="80d90-107">A <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> should be supplied, either through adding the attribute directly to the assembly or by specifying a target framework in the [project file or through Visual Studio's project properties GUI](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).</span></span>

| <span data-ttu-id="80d90-108">name</span><span class="sxs-lookup"><span data-stu-id="80d90-108">Name</span></span>    | <span data-ttu-id="80d90-109">Wert</span><span class="sxs-lookup"><span data-stu-id="80d90-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80d90-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="80d90-110">Scope</span></span>   |<span data-ttu-id="80d90-111">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="80d90-111">Major</span></span>|
|<span data-ttu-id="80d90-112">Version</span><span class="sxs-lookup"><span data-stu-id="80d90-112">Version</span></span>|<span data-ttu-id="80d90-113">4.5</span><span class="sxs-lookup"><span data-stu-id="80d90-113">4.5</span></span>|
|<span data-ttu-id="80d90-114">Typ</span><span class="sxs-lookup"><span data-stu-id="80d90-114">Type</span></span>|<span data-ttu-id="80d90-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="80d90-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="80d90-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="80d90-116">Affected APIs</span></span>

<span data-ttu-id="80d90-117">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="80d90-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
