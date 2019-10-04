---
ms.openlocfilehash: 2a751acc129ebd1c917b87f8083ffef72c7d8c17
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216360"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="94eb3-101">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="94eb3-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="94eb3-102">Viele APIs, die in .NET Core Versionsinformationen zurückgeben, geben nun anstelle der Dateiversion die Produktversion zurück.</span><span class="sxs-lookup"><span data-stu-id="94eb3-102">Many of the APIs that return versions in .NET Core now returned the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="94eb3-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="94eb3-103">Change description</span></span>

<span data-ttu-id="94eb3-104">In .NET Core 2.2 und früheren Versionen, wird in Methoden wie <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> und im Dialogfeld mit den Dateieigenschaften für .NET Core-Assemblys die Dateiversion angegeben.</span><span class="sxs-lookup"><span data-stu-id="94eb3-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="94eb3-105">Ab .NET Core 3.0 wird die Produktversion angegeben.</span><span class="sxs-lookup"><span data-stu-id="94eb3-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="94eb3-106">In der folgenden Abbildung sind die unterschiedlichen Versionsinformationen für die *System.Runtime.dll*-Assembly für .NET Core 2.2 (links) und .NET Core 3.0 (rechts) zu sehen, die im Dialogfeld mit Dateieigenschaften im **Windows-Explorer** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="94eb3-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![Unterschiedliche Produktversionsinformationen](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="94eb3-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="94eb3-108">Version introduced</span></span>

<span data-ttu-id="94eb3-109">3.0</span><span class="sxs-lookup"><span data-stu-id="94eb3-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="94eb3-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="94eb3-110">Recommended action</span></span>

<span data-ttu-id="94eb3-111">Keine</span><span class="sxs-lookup"><span data-stu-id="94eb3-111">None.</span></span> <span data-ttu-id="94eb3-112">Durch diese Änderung soll die Version einfacher und intuitiver zu erkennen sein.</span><span class="sxs-lookup"><span data-stu-id="94eb3-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="94eb3-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="94eb3-113">Category</span></span>

<span data-ttu-id="94eb3-114">CoreFx</span><span class="sxs-lookup"><span data-stu-id="94eb3-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="94eb3-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="94eb3-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
