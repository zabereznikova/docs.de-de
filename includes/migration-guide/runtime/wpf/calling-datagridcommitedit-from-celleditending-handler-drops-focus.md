---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497805"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="4444c-101">Der Aufruf von DataGrid.CommitEdit über einen CellEditEnding-Handler verliert den Fokus</span><span class="sxs-lookup"><span data-stu-id="4444c-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="4444c-102">Details</span><span class="sxs-lookup"><span data-stu-id="4444c-102">Details</span></span>

<span data-ttu-id="4444c-103">Wenn das <xref:System.Windows.Controls.DataGrid.CommitEdit>-Element von einem der <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName>-Ereignishandler von <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> aufgerufen, verliert <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> den Fokus.</span><span class="sxs-lookup"><span data-stu-id="4444c-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4444c-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4444c-104">Suggestion</span></span>

<span data-ttu-id="4444c-105">Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="4444c-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="4444c-106">Alternativ kann dies vermieden werden, indem das <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>-Element nach dem Aufruf von <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName> explizit neu ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="4444c-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="4444c-107">name</span><span class="sxs-lookup"><span data-stu-id="4444c-107">Name</span></span>    | <span data-ttu-id="4444c-108">Wert</span><span class="sxs-lookup"><span data-stu-id="4444c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4444c-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="4444c-109">Scope</span></span>   |<span data-ttu-id="4444c-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4444c-110">Edge</span></span>|
|<span data-ttu-id="4444c-111">Version</span><span class="sxs-lookup"><span data-stu-id="4444c-111">Version</span></span>|<span data-ttu-id="4444c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="4444c-112">4.5</span></span>|
|<span data-ttu-id="4444c-113">Typ</span><span class="sxs-lookup"><span data-stu-id="4444c-113">Type</span></span>|<span data-ttu-id="4444c-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="4444c-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4444c-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4444c-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
