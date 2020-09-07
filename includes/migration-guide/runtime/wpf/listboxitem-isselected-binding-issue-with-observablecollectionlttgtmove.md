---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496529"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a><span data-ttu-id="c46d5-101">IsSelected-Bindungsfehler für ListBoxItem mit ObservableCollection&lt;T&gt;.Move</span><span class="sxs-lookup"><span data-stu-id="c46d5-101">ListBoxItem IsSelected binding issue with ObservableCollection&lt;T&gt;.Move</span></span>

#### <a name="details"></a><span data-ttu-id="c46d5-102">Details</span><span class="sxs-lookup"><span data-stu-id="c46d5-102">Details</span></span>

<span data-ttu-id="c46d5-103">Wenn <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> oder <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> für eine Auflistung aufgerufen werden, die über aktivierte Elemente an ein <xref:System.Windows.Controls.ListBox?displayProperty=fullName>-Element gebunden ist, können bei der (De-)Aktivierung von <xref:System.Windows.Controls.ListBox?displayProperty=fullName>-Elementen Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="c46d5-103">Calling <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> or <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> on a collection bound to a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> with items selected can lead to erratic behavior with future selection or unselection of <xref:System.Windows.Controls.ListBox?displayProperty=fullName> items.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c46d5-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c46d5-104">Suggestion</span></span>

<span data-ttu-id="c46d5-105">Wenn Sie anstelle von <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)><xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> und <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> aufrufen, kann dieser Fehler umgangen werden.</span><span class="sxs-lookup"><span data-stu-id="c46d5-105">Calling <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> and <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> instead of <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> will work around this issue.</span></span> <span data-ttu-id="c46d5-106">Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="c46d5-106">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="c46d5-107">name</span><span class="sxs-lookup"><span data-stu-id="c46d5-107">Name</span></span>    | <span data-ttu-id="c46d5-108">Wert</span><span class="sxs-lookup"><span data-stu-id="c46d5-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c46d5-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="c46d5-109">Scope</span></span>   |<span data-ttu-id="c46d5-110">Gering</span><span class="sxs-lookup"><span data-stu-id="c46d5-110">Minor</span></span>|
|<span data-ttu-id="c46d5-111">Version</span><span class="sxs-lookup"><span data-stu-id="c46d5-111">Version</span></span>|<span data-ttu-id="c46d5-112">4.5</span><span class="sxs-lookup"><span data-stu-id="c46d5-112">4.5</span></span>|
|<span data-ttu-id="c46d5-113">Typ</span><span class="sxs-lookup"><span data-stu-id="c46d5-113">Type</span></span>|<span data-ttu-id="c46d5-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c46d5-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c46d5-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c46d5-115">Affected APIs</span></span>

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
