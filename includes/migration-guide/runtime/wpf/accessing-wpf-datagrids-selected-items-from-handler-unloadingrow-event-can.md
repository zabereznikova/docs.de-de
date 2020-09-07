---
ms.openlocfilehash: 1487e32ffca7b4bbebb5edac7efc8961ac05723b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497011"
---
### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a><span data-ttu-id="7364c-101">Der Zugriff auf die ausgewählten Elemente eines WPF-DataGrid-Steuerelements über einen Handler des UnloadingRow-Ereignisses kann eine NullReferenceException auslösen</span><span class="sxs-lookup"><span data-stu-id="7364c-101">Accessing a WPF DataGrid's selected items from a handler of the DataGrid's UnloadingRow event can cause a NullReferenceException</span></span>

#### <a name="details"></a><span data-ttu-id="7364c-102">Details</span><span class="sxs-lookup"><span data-stu-id="7364c-102">Details</span></span>

<span data-ttu-id="7364c-103">Aufgrund eines Fehlers in .NET Framework 4.5 können Ereignishandler für <xref:System.Windows.Controls.DataGrid>-Ereignisse, die das Entfernen einer Zeile umfassen, eine <xref:System.NullReferenceException?displayProperty=fullName> auslösen, die ausgelöst werden soll, wenn auf die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName>- oder <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName>-Eigenschaft von <xref:System.Windows.Controls.DataGrid> zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="7364c-103">Due to a bug in the .NET Framework 4.5, event handlers for <xref:System.Windows.Controls.DataGrid> events involving the removal of a row can cause a <xref:System.NullReferenceException?displayProperty=fullName> to be thrown if they access the <xref:System.Windows.Controls.DataGrid>'s <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=fullName> or <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=fullName> properties.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7364c-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7364c-104">Suggestion</span></span>

<span data-ttu-id="7364c-105">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="7364c-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="7364c-106">name</span><span class="sxs-lookup"><span data-stu-id="7364c-106">Name</span></span>    | <span data-ttu-id="7364c-107">Wert</span><span class="sxs-lookup"><span data-stu-id="7364c-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7364c-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="7364c-108">Scope</span></span>   |<span data-ttu-id="7364c-109">Gering</span><span class="sxs-lookup"><span data-stu-id="7364c-109">Minor</span></span>|
|<span data-ttu-id="7364c-110">Version</span><span class="sxs-lookup"><span data-stu-id="7364c-110">Version</span></span>|<span data-ttu-id="7364c-111">4.5</span><span class="sxs-lookup"><span data-stu-id="7364c-111">4.5</span></span>|
|<span data-ttu-id="7364c-112">Typ</span><span class="sxs-lookup"><span data-stu-id="7364c-112">Type</span></span>|<span data-ttu-id="7364c-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7364c-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7364c-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7364c-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.Controls.DataGrid.UnloadingRow`
- `E:System.Windows.Controls.DataGrid.UnloadingRowDetails`

-->
