---
ms.openlocfilehash: cda5df4b673412a7c8c59f80f89c19c13dc81dc1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235544"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="3799d-101">Der Zugriff auf die ausgewählten Elemente eines WPF-DataGrid-Steuerelements über einen Handler des UnloadingRow-Ereignisses kann eine NullReferenceException auslösen</span><span class="sxs-lookup"><span data-stu-id="3799d-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3799d-102">Details</span><span class="sxs-lookup"><span data-stu-id="3799d-102">Details</span></span>|<span data-ttu-id="3799d-103">Aufgrund eines Fehlers in .NET Framework 4.5 können Ereignishandler für <xref:System.Windows.Controls.DataGrid>-Ereignisse, die das Entfernen einer Zeile umfassen, eine <xref:System.NullReferenceException?displayProperty=name> auslösen, die ausgelöst werden soll, wenn auf die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name>- oder <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name>-Eigenschaft von <xref:System.Windows.Controls.DataGrid> zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="3799d-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=name> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> properties.</span></span>|
|<span data-ttu-id="3799d-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3799d-104">Suggestion</span></span>|<span data-ttu-id="3799d-105">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="3799d-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="3799d-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="3799d-106">Scope</span></span>|<span data-ttu-id="3799d-107">Gering</span><span class="sxs-lookup"><span data-stu-id="3799d-107">Minor</span></span>|
|<span data-ttu-id="3799d-108">Version</span><span class="sxs-lookup"><span data-stu-id="3799d-108">Version</span></span>|<span data-ttu-id="3799d-109">4.5</span><span class="sxs-lookup"><span data-stu-id="3799d-109">4.5</span></span>|
|<span data-ttu-id="3799d-110">Typ</span><span class="sxs-lookup"><span data-stu-id="3799d-110">Type</span></span>|<span data-ttu-id="3799d-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3799d-111">Runtime</span></span>|
|<span data-ttu-id="3799d-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3799d-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|
