---
title: 'Breaking Change: Der Wert von FrameworkDescription entspricht „.NET“ anstelle von „.NET Core“'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den RuntimeInformation.FrameworkDescription jetzt „.NET“ anstelle von „NET Core“ zurückgibt.
ms.date: 11/01/2020
ms.openlocfilehash: 3925fb092135c26291e1e60b99f359974d21553c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759485"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="c4cdd-103">Der Wert von FrameworkDescription entspricht „.NET“ anstelle von „.NET Core“</span><span class="sxs-lookup"><span data-stu-id="c4cdd-103">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="c4cdd-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> gibt jetzt „.NET“ anstelle von „.NET Core“ zurück.</span><span class="sxs-lookup"><span data-stu-id="c4cdd-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

## <a name="change-description"></a><span data-ttu-id="c4cdd-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="c4cdd-105">Change description</span></span>

<span data-ttu-id="c4cdd-106">In früheren Versionen von .NET gibt <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> „.NET Core“ als Teil der Beschreibungszeichenfolge zurück, z. B. `.NET Core 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="c4cdd-106">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="c4cdd-107">Ab .NET 5.0 gibt <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> „.NET“ als Teil der Beschreibungszeichenfolge zurück, z. B. `.NET 5.0.0`.</span><span class="sxs-lookup"><span data-stu-id="c4cdd-107">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="c4cdd-108">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="c4cdd-108">Reason for change</span></span>

<span data-ttu-id="c4cdd-109">Mit .NET 5 wird `netcoreapp` durch `net` als Zielframeworkmoniker ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c4cdd-109">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="c4cdd-110">Aus Konsistenzgründen wurde die Beschreibung des Frameworks ebenfalls aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c4cdd-110">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="c4cdd-111">Die Änderung ist rein kosmetischer Natur, da der `FrameworkName` nur in der Eigenschaft <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> codiert wird.</span><span class="sxs-lookup"><span data-stu-id="c4cdd-111">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="c4cdd-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="c4cdd-112">Version introduced</span></span>

<span data-ttu-id="c4cdd-113">5.0</span><span class="sxs-lookup"><span data-stu-id="c4cdd-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="c4cdd-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="c4cdd-114">Recommended action</span></span>

<span data-ttu-id="c4cdd-115">Aktualisieren Sie jeglichen Code, mit dem in der von <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> zurückgegebenen Zeichenfolge nach „.NET Core“ gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="c4cdd-115">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="c4cdd-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c4cdd-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
