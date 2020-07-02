---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620472"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="1889d-101">WPF DataTemplate-Elemente sind jetzt für die UIA sichtbar</span><span class="sxs-lookup"><span data-stu-id="1889d-101">WPF DataTemplate elements are now visible to UIA</span></span>

#### <a name="details"></a><span data-ttu-id="1889d-102">Details</span><span class="sxs-lookup"><span data-stu-id="1889d-102">Details</span></span>

<span data-ttu-id="1889d-103">In der Vergangenheit waren <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente für die Benutzeroberflächenautomatisierung nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="1889d-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=fullName> elements were invisible to UI Automation.</span></span> <span data-ttu-id="1889d-104">Ab Version 4.5 erkennt die Benutzeroberflächenautomatisierung diese Elemente.</span><span class="sxs-lookup"><span data-stu-id="1889d-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="1889d-105">Dies ist zwar in vielen Fällen hilfreich, kann aber bei Tests zu Problemen führen, die von UIA-Strukturen abhängen, die keine <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="1889d-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1889d-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1889d-106">Suggestion</span></span>

<span data-ttu-id="1889d-107">Tests für die Benutzeroberflächenautomatisierung für diese App müssen möglicherweise aktualisiert werden, um die UIA-Struktur zu berücksichtigen, die jetzt zuvor unsichtbare <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="1889d-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span> <span data-ttu-id="1889d-108">Beispielsweise müssen Tests, die erwarten, dass einige Elemente nebeneinander angeordnet sind, jetzt möglicherweise davon ausgehen, dass sich zwischen diesen Elementen zuvor unsichtbare UIA-Elemente befinden.</span><span class="sxs-lookup"><span data-stu-id="1889d-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="1889d-109">Möglicherweise müssen auch Tests mit neuen Werten aktualisiert werden, die auf bestimmte Werte oder Indizes für UIA-Elemente angewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="1889d-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>

| <span data-ttu-id="1889d-110">name</span><span class="sxs-lookup"><span data-stu-id="1889d-110">Name</span></span>    | <span data-ttu-id="1889d-111">Wert</span><span class="sxs-lookup"><span data-stu-id="1889d-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1889d-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="1889d-112">Scope</span></span>   |<span data-ttu-id="1889d-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1889d-113">Edge</span></span>|
|<span data-ttu-id="1889d-114">Version</span><span class="sxs-lookup"><span data-stu-id="1889d-114">Version</span></span>|<span data-ttu-id="1889d-115">4.5</span><span class="sxs-lookup"><span data-stu-id="1889d-115">4.5</span></span>|
|<span data-ttu-id="1889d-116">Typ</span><span class="sxs-lookup"><span data-stu-id="1889d-116">Type</span></span>|<span data-ttu-id="1889d-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1889d-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1889d-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1889d-118">Affected APIs</span></span>

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
