---
ms.openlocfilehash: 25ce391f917bd270d4d9a75f608e4a8ec763d15c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497149"
---
### <a name="itemsclear-does-not-remove-duplicates-from-selecteditems"></a><span data-ttu-id="a741b-101">Items.Clear entfernt keine Duplikate aus SelectedItems</span><span class="sxs-lookup"><span data-stu-id="a741b-101">Items.Clear does not remove duplicates from SelectedItems</span></span>

#### <a name="details"></a><span data-ttu-id="a741b-102">Details</span><span class="sxs-lookup"><span data-stu-id="a741b-102">Details</span></span>

<span data-ttu-id="a741b-103">Angenommen, ein Selektor (mit aktivierter Mehrfachauswahl) verfügt in seiner <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>-Sammlung über Duplikate, sodass das gleiche Element mehrmals angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a741b-103">Suppose a Selector (with multiple selection enabled) has duplicates in its <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> collection - the same item appears more than once.</span></span>  <span data-ttu-id="a741b-104">Beim Entfernen dieser Elemente aus der Datenquelle (z.B. durch Aufrufen von Items.Clear) werden sie dann nicht aus <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> entfernt. Es wird nur die erste Instanz entfernt.</span><span class="sxs-lookup"><span data-stu-id="a741b-104">Removing those items from the data source (e.g. by calling Items.Clear) fails to remove them from <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>; only the first instance is removed.</span></span> <span data-ttu-id="a741b-105">Darüber hinaus kann die anschließende Verwendung von <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (z.B. SelectedItems.Clear()) Probleme wie <xref:System.ArgumentException?displayProperty=fullName> verursachen, da <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> Elemente enthält, die sich nicht mehr in der Datenquelle befinden.</span><span class="sxs-lookup"><span data-stu-id="a741b-105">Furthermore, subsequent use of <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> (e.g. SelectedItems.Clear()) can encounter problems such as <xref:System.ArgumentException?displayProperty=fullName>, because <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> contains items that are no longer in the data source.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a741b-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a741b-106">Suggestion</span></span>

<span data-ttu-id="a741b-107">Führen Sie nach Möglichkeit ein Upgrade auf .NET 4.6.2 durch.</span><span class="sxs-lookup"><span data-stu-id="a741b-107">Upgrade if possible to .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="a741b-108">name</span><span class="sxs-lookup"><span data-stu-id="a741b-108">Name</span></span>    | <span data-ttu-id="a741b-109">Wert</span><span class="sxs-lookup"><span data-stu-id="a741b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a741b-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="a741b-110">Scope</span></span>   |<span data-ttu-id="a741b-111">Gering</span><span class="sxs-lookup"><span data-stu-id="a741b-111">Minor</span></span>|
|<span data-ttu-id="a741b-112">Version</span><span class="sxs-lookup"><span data-stu-id="a741b-112">Version</span></span>|<span data-ttu-id="a741b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="a741b-113">4.5</span></span>|
|<span data-ttu-id="a741b-114">Typ</span><span class="sxs-lookup"><span data-stu-id="a741b-114">Type</span></span>|<span data-ttu-id="a741b-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a741b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a741b-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a741b-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.MultiSelector.SelectedItems`

-->
