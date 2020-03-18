---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858485"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="66019-101">Der Zugriff auf die ausgewählten Elemente eines WPF-DataGrid-Steuerelements über einen Handler des UnloadingRow-Ereignisses kann eine NullReferenceException auslösen</span><span class="sxs-lookup"><span data-stu-id="66019-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="66019-102">Details</span><span class="sxs-lookup"><span data-stu-id="66019-102">Details</span></span>|<span data-ttu-id="66019-103">Aufgrund eines Fehlers in .NET Framework 4.5 können Ereignishandler für <xref:System.Windows.Controls.DataGrid>-Ereignisse, die das Entfernen einer Zeile umfassen, eine <xref:System.NullReferenceException?displayProperty=name> auslösen, die ausgelöst werden soll, wenn auf die <xref:System.Windows.Controls.DataGrid>- oder <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name>-Eigenschaft von <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="66019-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=name> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> properties.</span></span>|
|<span data-ttu-id="66019-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="66019-104">Suggestion</span></span>|<span data-ttu-id="66019-105">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="66019-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="66019-106">`Scope`</span><span class="sxs-lookup"><span data-stu-id="66019-106">Scope</span></span>|<span data-ttu-id="66019-107">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="66019-107">Minor</span></span>|
|<span data-ttu-id="66019-108">Version</span><span class="sxs-lookup"><span data-stu-id="66019-108">Version</span></span>|<span data-ttu-id="66019-109">4.5</span><span class="sxs-lookup"><span data-stu-id="66019-109">4.5</span></span>|
|<span data-ttu-id="66019-110">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="66019-110">Type</span></span>|<span data-ttu-id="66019-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="66019-111">Runtime</span></span>|
|<span data-ttu-id="66019-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="66019-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
