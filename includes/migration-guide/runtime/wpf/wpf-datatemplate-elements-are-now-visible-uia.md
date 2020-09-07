---
ms.openlocfilehash: 4394e69dafeb6cce2d7719a67bbce396d3bc1086
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497066"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="440e9-101">WPF DataTemplate-Elemente sind jetzt für die UIA sichtbar</span><span class="sxs-lookup"><span data-stu-id="440e9-101">WPF DataTemplate elements are now visible to UIA</span></span>

#### <a name="details"></a><span data-ttu-id="440e9-102">Details</span><span class="sxs-lookup"><span data-stu-id="440e9-102">Details</span></span>

<span data-ttu-id="440e9-103">In der Vergangenheit waren <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente für die Benutzeroberflächenautomatisierung nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="440e9-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=fullName> elements were invisible to UI Automation.</span></span> <span data-ttu-id="440e9-104">Ab Version 4.5 erkennt die Benutzeroberflächenautomatisierung diese Elemente.</span><span class="sxs-lookup"><span data-stu-id="440e9-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="440e9-105">Dies ist zwar in vielen Fällen hilfreich, kann aber bei Tests zu Problemen führen, die von UIA-Strukturen abhängen, die keine <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="440e9-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="440e9-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="440e9-106">Suggestion</span></span>

<span data-ttu-id="440e9-107">Tests für die Benutzeroberflächenautomatisierung für diese App müssen möglicherweise aktualisiert werden, um die UIA-Struktur zu berücksichtigen, die jetzt zuvor unsichtbare <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="440e9-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span> <span data-ttu-id="440e9-108">Beispielsweise müssen Tests, die erwarten, dass einige Elemente nebeneinander angeordnet sind, jetzt möglicherweise davon ausgehen, dass sich zwischen diesen Elementen zuvor unsichtbare UIA-Elemente befinden.</span><span class="sxs-lookup"><span data-stu-id="440e9-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="440e9-109">Möglicherweise müssen auch Tests mit neuen Werten aktualisiert werden, die auf bestimmte Werte oder Indizes für UIA-Elemente angewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="440e9-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>

| <span data-ttu-id="440e9-110">name</span><span class="sxs-lookup"><span data-stu-id="440e9-110">Name</span></span>    | <span data-ttu-id="440e9-111">Wert</span><span class="sxs-lookup"><span data-stu-id="440e9-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="440e9-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="440e9-112">Scope</span></span>   |<span data-ttu-id="440e9-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="440e9-113">Edge</span></span>|
|<span data-ttu-id="440e9-114">Version</span><span class="sxs-lookup"><span data-stu-id="440e9-114">Version</span></span>|<span data-ttu-id="440e9-115">4.5</span><span class="sxs-lookup"><span data-stu-id="440e9-115">4.5</span></span>|
|<span data-ttu-id="440e9-116">Typ</span><span class="sxs-lookup"><span data-stu-id="440e9-116">Type</span></span>|<span data-ttu-id="440e9-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="440e9-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="440e9-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="440e9-118">Affected APIs</span></span>

- <xref:System.Windows.DataTemplate.%23ctor>
- <xref:System.Windows.DataTemplate.%23ctor(System.Object)>

<!--

#### Affected APIs

- `M:System.Windows.DataTemplate.#ctor`
- `M:System.Windows.DataTemplate.#ctor(System.Object)`

-->
