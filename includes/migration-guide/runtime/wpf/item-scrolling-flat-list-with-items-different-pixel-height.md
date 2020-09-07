---
ms.openlocfilehash: d23d7821e19b9d7f2db13a6bfdf868a8414cf721
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496697"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a><span data-ttu-id="55cf9-101">Elementscrolling durch eine flache Liste mit Elementen mit unterschiedlicher Pixelhöhe</span><span class="sxs-lookup"><span data-stu-id="55cf9-101">Item-scrolling a flat list with items of different pixel-height</span></span>

#### <a name="details"></a><span data-ttu-id="55cf9-102">Details</span><span class="sxs-lookup"><span data-stu-id="55cf9-102">Details</span></span>

<span data-ttu-id="55cf9-103">Wenn ein <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>-Element eine Sammlung mithilfe von Virtualisierung (<code>IsVirtualizing=true</code>) und Elementscrolling (<code>ScrollUnit=Item</code>) anzeigt, und wenn das Steuerelement gescrollt wird, um ein Element anzuzeigen, dessen Größe in Pixeln sich von dessen Nachbarn unterscheidet, durchläuft <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> alle Elemente in der Sammlung.</span><span class="sxs-lookup"><span data-stu-id="55cf9-103">When an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> displays a collection using virtualization (<code>IsVirtualizing=true</code>) and item- scrolling (<code>ScrollUnit=Item</code>), and when the control scrolls to display an item whose height in pixels differs from its neighbors, the <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> iterates over all items in the collection.</span></span> <span data-ttu-id="55cf9-104">Die Benutzeroberfläche reagiert während dieser Iteration nicht. Wenn die Sammlung groß ist, kann dies als Absturz wahrgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="55cf9-104">The UI is unresponsive during this iteration; if the collection is large, this can be perceived as a hang.</span></span> <span data-ttu-id="55cf9-105">Die Iteration tritt auch in anderen Fällen und selbst in früheren .NET Framework-Releases auf.</span><span class="sxs-lookup"><span data-stu-id="55cf9-105">The iteration occurs in other circumstances, even in previous .NET Framework releases.</span></span> <span data-ttu-id="55cf9-106">Sie tritt z.B. beim Scrollen von Pixeln (<code>ScrollUnit=Pixel</code>) auf, nachdem ein Element mit einer anderen Pixelhöhe erkannt wurde sowie beim Elementscrolling für hierarchische Daten (wie beim <xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Steuerelement oder einem <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName>-Element mit aktivierter Gruppierung), nachdem bei einem Element eine andere Anzahl von Nachfolgerelementen als bei seinen Nachbarn erkannt wurde. Im Fall des Elementscrollings bei unterschiedlicher Pixelhöhe wurde die Iteration in .NET Framework 4.6.1 eingeführt, um Fehler im Layout der hierarchischen Daten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="55cf9-106">For example, it occurs when pixel-scrolling (<code>ScrollUnit=Pixel</code>) upon encountering an item with different pixel height, and when item-scrolling hierarchical data (such as a <xref:System.Windows.Controls.TreeView?displayProperty=fullName> or an <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> with grouping enabled) upon encountering an item with a different number of descendant items than its neighbors.For the case of item-scrolling and different pixel height, the iteration was introduced in .NET Framework 4.6.1 to fix bugs in the layout of hierarchical data.</span></span>  <span data-ttu-id="55cf9-107">Dies ist für flache Datenstrukturen (ohne Hierarchie) nicht erforderlich, und .NET Framework 4.6.2 führt die Iteration in diesem Fall nicht aus.</span><span class="sxs-lookup"><span data-stu-id="55cf9-107">It is not needed if the data is flat (no hierarchy), and .NET Framework 4.6.2 does not do it in that case.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="55cf9-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="55cf9-108">Suggestion</span></span>

<span data-ttu-id="55cf9-109">Wenn die Iteration in .NET Framework 4.6.1, aber nicht in früheren Releases auftritt, also wenn <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> das Elementscrolling in einer flachen Liste von Elementen mit unterschiedlicher Pixelhöhe durchführt, gibt es zwei Lösungen:</span><span class="sxs-lookup"><span data-stu-id="55cf9-109">If the iteration occurs in .NET Framework 4.6.1 but not in earlier releases - that is, if the <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> is item- scrolling a flat list with items of different pixel height - there are two remedies:</span></span><ol><li><span data-ttu-id="55cf9-110">.NET Framework 4.6.2 installieren</span><span class="sxs-lookup"><span data-stu-id="55cf9-110">Install .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="55cf9-111">Hotfix HR 1605 für .NET Framework 4.6.1 installieren</span><span class="sxs-lookup"><span data-stu-id="55cf9-111">Install hotfix HR 1605 for .NET Framework 4.6.1.</span></span></li></ol>

| <span data-ttu-id="55cf9-112">name</span><span class="sxs-lookup"><span data-stu-id="55cf9-112">Name</span></span>    | <span data-ttu-id="55cf9-113">Wert</span><span class="sxs-lookup"><span data-stu-id="55cf9-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="55cf9-114">Bereich</span><span class="sxs-lookup"><span data-stu-id="55cf9-114">Scope</span></span>   |<span data-ttu-id="55cf9-115">Gering</span><span class="sxs-lookup"><span data-stu-id="55cf9-115">Minor</span></span>|
|<span data-ttu-id="55cf9-116">Version</span><span class="sxs-lookup"><span data-stu-id="55cf9-116">Version</span></span>|<span data-ttu-id="55cf9-117">4.6.1</span><span class="sxs-lookup"><span data-stu-id="55cf9-117">4.6.1</span></span>|
|<span data-ttu-id="55cf9-118">Typ</span><span class="sxs-lookup"><span data-stu-id="55cf9-118">Type</span></span>|<span data-ttu-id="55cf9-119">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="55cf9-119">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="55cf9-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="55cf9-120">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.VirtualizingStackPanel`

-->
