---
ms.openlocfilehash: 80d13609f1b02ae0ac875b2028e745670bb8f503
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050564"
---
### <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="ccc79-101">Der Wert von FrameworkDescription entspricht „.NET“ anstelle von „.NET Core“</span><span class="sxs-lookup"><span data-stu-id="ccc79-101">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="ccc79-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> gibt jetzt „.NET“ anstelle von „.NET Core“ zurück.</span><span class="sxs-lookup"><span data-stu-id="ccc79-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

#### <a name="change-description"></a><span data-ttu-id="ccc79-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ccc79-103">Change description</span></span>

<span data-ttu-id="ccc79-104">In früheren Versionen von .NET gibt <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> „.NET Core“ als Teil der Beschreibungszeichenfolge zurück, z. B. `.NET Core 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="ccc79-104">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="ccc79-105">Ab .NET 5.0 gibt <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> „.NET“ als Teil der Beschreibungszeichenfolge zurück, z. B. `.NET 5.0.0`.</span><span class="sxs-lookup"><span data-stu-id="ccc79-105">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ccc79-106">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="ccc79-106">Reason for change</span></span>

<span data-ttu-id="ccc79-107">Mit .NET 5 wird `netcoreapp` durch `net` als Zielframeworkmoniker ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ccc79-107">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="ccc79-108">Aus Konsistenzgründen wurde die Beschreibung des Frameworks ebenfalls aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ccc79-108">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="ccc79-109">Die Änderung ist rein kosmetischer Natur, da der `FrameworkName` nur in der Eigenschaft <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> codiert wird.</span><span class="sxs-lookup"><span data-stu-id="ccc79-109">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ccc79-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="ccc79-110">Version introduced</span></span>

<span data-ttu-id="ccc79-111">5.0</span><span class="sxs-lookup"><span data-stu-id="ccc79-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ccc79-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="ccc79-112">Recommended action</span></span>

<span data-ttu-id="ccc79-113">Aktualisieren Sie jeglichen Code, mit dem in der von <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> zurückgegebenen Zeichenfolge nach „.NET Core“ gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="ccc79-113">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

#### <a name="category"></a><span data-ttu-id="ccc79-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="ccc79-114">Category</span></span>

<span data-ttu-id="ccc79-115">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="ccc79-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ccc79-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ccc79-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
