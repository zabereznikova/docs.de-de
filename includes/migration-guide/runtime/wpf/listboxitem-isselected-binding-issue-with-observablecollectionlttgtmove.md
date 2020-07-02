---
ms.openlocfilehash: f4ff938b2d0e9ead481fdf239aed8a6b918a99b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620448"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="027db-101">IsSelected-Bindungsfehler für ListBoxItem mit ObservableCollection&lt;T&gt;.Move</span><span class="sxs-lookup"><span data-stu-id="027db-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="027db-102">Details</span><span class="sxs-lookup"><span data-stu-id="027db-102">Details</span></span>

<span data-ttu-id="027db-103">Wenn <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> oder <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> für eine Auflistung aufgerufen werden, die über aktivierte Elemente an ein <xref:System.Windows.Controls.ListBox?displayProperty=fullName>-Element gebunden ist, können bei der (De-)Aktivierung von <xref:System.Windows.Controls.ListBox?displayProperty=fullName>-Elementen Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="027db-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="027db-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="027db-104">Suggestion</span></span>

<span data-ttu-id="027db-105">Wenn Sie anstelle von <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)><xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> und <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> aufrufen, kann dieser Fehler umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="027db-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="027db-106">Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="027db-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="027db-107">name</span><span class="sxs-lookup"><span data-stu-id="027db-107">Name</span></span>    | <span data-ttu-id="027db-108">Wert</span><span class="sxs-lookup"><span data-stu-id="027db-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="027db-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="027db-109">Scope</span></span>   |<span data-ttu-id="027db-110">Gering</span><span class="sxs-lookup"><span data-stu-id="027db-110">Minor</span></span>|
|<span data-ttu-id="027db-111">Version</span><span class="sxs-lookup"><span data-stu-id="027db-111">Version</span></span>|<span data-ttu-id="027db-112">4.5</span><span class="sxs-lookup"><span data-stu-id="027db-112">4.5</span></span>|
|<span data-ttu-id="027db-113">Typ</span><span class="sxs-lookup"><span data-stu-id="027db-113">Type</span></span>|<span data-ttu-id="027db-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="027db-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="027db-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="027db-115">Affected APIs</span></span>

-<xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
