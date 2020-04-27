---
ms.openlocfilehash: 1580c8c8b7bdad91656f494537230293dbaaf93b
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021551"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="2fc1f-101">APIs, die Versionsinformationen melden, melden nun die Produktversion und nicht die Dateiversion</span><span class="sxs-lookup"><span data-stu-id="2fc1f-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="2fc1f-102">Viele APIs, die in .NET Core Versionsinformationen zurückgeben, geben nun anstelle der Dateiversion die Produktversion zurück.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-102">Many of the APIs that return versions in .NET Core now return the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2fc1f-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="2fc1f-103">Change description</span></span>

<span data-ttu-id="2fc1f-104">In .NET Core 2.2 und früheren Versionen, wird in Methoden wie <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> und im Dialogfeld mit den Dateieigenschaften für .NET Core-Assemblys die Dateiversion angegeben.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="2fc1f-105">Ab .NET Core 3.0 wird die Produktversion angegeben.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="2fc1f-106">In der folgenden Abbildung sind die unterschiedlichen Versionsinformationen für die *System.Runtime.dll*-Assembly für .NET Core 2.2 (links) und .NET Core 3.0 (rechts) zu sehen, die im Dialogfeld mit Dateieigenschaften im **Windows-Explorer** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![Unterschiedliche Produktversionsinformationen](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="2fc1f-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="2fc1f-108">Version introduced</span></span>

<span data-ttu-id="2fc1f-109">3.0</span><span class="sxs-lookup"><span data-stu-id="2fc1f-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2fc1f-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="2fc1f-110">Recommended action</span></span>

<span data-ttu-id="2fc1f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="2fc1f-111">None.</span></span> <span data-ttu-id="2fc1f-112">Durch diese Änderung soll die Version einfacher und intuitiver zu erkennen sein.</span><span class="sxs-lookup"><span data-stu-id="2fc1f-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="2fc1f-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="2fc1f-113">Category</span></span>

<span data-ttu-id="2fc1f-114">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="2fc1f-114">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2fc1f-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2fc1f-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
