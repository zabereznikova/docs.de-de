---
ms.openlocfilehash: 31ada197db36be192317e32a37a353d375d9cc65
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497823"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="2f3e5-101">Das Scrollen für ein WPF-TreeView-Steuerelement oder ein gruppiertes ListBox-Steuerelement in VirtualizingStackPanel kann zu einem Absturz führen</span><span class="sxs-lookup"><span data-stu-id="2f3e5-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="2f3e5-102">Details</span><span class="sxs-lookup"><span data-stu-id="2f3e5-102">Details</span></span>

<span data-ttu-id="2f3e5-103">Das Scrollen für ein WPF-<xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Element in .NET Framework 4.5 in einem virtualisierten StackPanel-Element kann zu einem Absturz führen, wenn im Anzeigebereich Ränder vorhanden sind (z.B. zwischen den Elementen in <xref:System.Windows.Controls.TreeView?displayProperty=fullName> oder für ein ItemsPresenter-Element).</span><span class="sxs-lookup"><span data-stu-id="2f3e5-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="2f3e5-104">Darüber hinaus können in einigen Fällen Elemente unterschiedlicher Größe in der Ansicht zur Instabilität führen, auch wenn keine Ränder vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2f3e5-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2f3e5-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2f3e5-105">Suggestion</span></span>

<span data-ttu-id="2f3e5-106">Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="2f3e5-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="2f3e5-107">Alternativ können Ränder aus Ansichtsauflistungen (z.B. mehreren <xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Elementen) in virtualisierten StackPanel-Elementen entfernt werden, wenn alle enthaltenen Elemente dieselbe Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2f3e5-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="2f3e5-108">name</span><span class="sxs-lookup"><span data-stu-id="2f3e5-108">Name</span></span>    | <span data-ttu-id="2f3e5-109">Wert</span><span class="sxs-lookup"><span data-stu-id="2f3e5-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2f3e5-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="2f3e5-110">Scope</span></span>   |<span data-ttu-id="2f3e5-111">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="2f3e5-111">Major</span></span>|
|<span data-ttu-id="2f3e5-112">Version</span><span class="sxs-lookup"><span data-stu-id="2f3e5-112">Version</span></span>|<span data-ttu-id="2f3e5-113">4.5</span><span class="sxs-lookup"><span data-stu-id="2f3e5-113">4.5</span></span>|
|<span data-ttu-id="2f3e5-114">Typ</span><span class="sxs-lookup"><span data-stu-id="2f3e5-114">Type</span></span>|<span data-ttu-id="2f3e5-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2f3e5-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2f3e5-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2f3e5-116">Affected APIs</span></span>

- <xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)`

-->
