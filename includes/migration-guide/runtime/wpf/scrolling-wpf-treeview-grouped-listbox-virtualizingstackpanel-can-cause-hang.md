---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622055"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a><span data-ttu-id="cd063-101">Das Scrollen für ein WPF-TreeView-Steuerelement oder ein gruppiertes ListBox-Steuerelement in VirtualizingStackPanel kann zu einem Absturz führen</span><span class="sxs-lookup"><span data-stu-id="cd063-101">Scrolling a WPF TreeView or grouped ListBox in a VirtualizingStackPanel can cause a hang</span></span>

#### <a name="details"></a><span data-ttu-id="cd063-102">Details</span><span class="sxs-lookup"><span data-stu-id="cd063-102">Details</span></span>

<span data-ttu-id="cd063-103">Das Scrollen für ein WPF-<xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Element in .NET Framework 4.5 in einem virtualisierten StackPanel-Element kann zu einem Absturz führen, wenn im Anzeigebereich Ränder vorhanden sind (z.B. zwischen den Elementen in <xref:System.Windows.Controls.TreeView?displayProperty=fullName> oder für ein ItemsPresenter-Element).</span><span class="sxs-lookup"><span data-stu-id="cd063-103">In the .NET Framework v4.5, scrolling a WPF <xref:System.Windows.Controls.TreeView?displayProperty=fullName> in a virtualized stack panel can cause hangs if there are margins in the viewport (between the items in the <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, for example, or on an ItemsPresenter element).</span></span> <span data-ttu-id="cd063-104">Darüber hinaus können in einigen Fällen Elemente unterschiedlicher Größe in der Ansicht zur Instabilität führen, auch wenn keine Ränder vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cd063-104">Additionally, in some cases, different sized items in the view can cause instability even if there are no margins.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cd063-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="cd063-105">Suggestion</span></span>

<span data-ttu-id="cd063-106">Dieser Fehler kann durch ein Upgrade auf .NET Framework 4.5.1 vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="cd063-106">This bug can be avoided by upgrading to .NET Framework 4.5.1.</span></span> <span data-ttu-id="cd063-107">Alternativ können Ränder aus Ansichtsauflistungen (z.B. mehreren <xref:System.Windows.Controls.TreeView?displayProperty=fullName>-Elementen) in virtualisierten StackPanel-Elementen entfernt werden, wenn alle enthaltenen Elemente dieselbe Größe aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cd063-107">Alternatively, margins can be removed from view collections (like <xref:System.Windows.Controls.TreeView?displayProperty=fullName>s) within virtualized stack panels if all contained items are the same size.</span></span>

| <span data-ttu-id="cd063-108">name</span><span class="sxs-lookup"><span data-stu-id="cd063-108">Name</span></span>    | <span data-ttu-id="cd063-109">Wert</span><span class="sxs-lookup"><span data-stu-id="cd063-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cd063-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="cd063-110">Scope</span></span>   |<span data-ttu-id="cd063-111">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="cd063-111">Major</span></span>|
|<span data-ttu-id="cd063-112">Version</span><span class="sxs-lookup"><span data-stu-id="cd063-112">Version</span></span>|<span data-ttu-id="cd063-113">4.5</span><span class="sxs-lookup"><span data-stu-id="cd063-113">4.5</span></span>|
|<span data-ttu-id="cd063-114">Typ</span><span class="sxs-lookup"><span data-stu-id="cd063-114">Type</span></span>|<span data-ttu-id="cd063-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="cd063-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd063-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="cd063-116">Affected APIs</span></span>

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
