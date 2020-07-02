---
ms.openlocfilehash: c3c3ed44cf53625c246dfe0408bb861750ecf336
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622026"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="369fb-101">Der Aufruf von DataGrid.CommitEdit über einen CellEditEnding-Handler verliert den Fokus</span><span class="sxs-lookup"><span data-stu-id="369fb-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="369fb-102">Details</span><span class="sxs-lookup"><span data-stu-id="369fb-102">Details</span></span>

<span data-ttu-id="369fb-103">Wenn das <xref:System.Windows.Controls.DataGrid.CommitEdit>-Element von einem der <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName>-Ereignishandler von <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> aufgerufen, verliert <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> den Fokus.</span><span class="sxs-lookup"><span data-stu-id="369fb-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="369fb-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="369fb-104">Suggestion</span></span>

<span data-ttu-id="369fb-105">Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="369fb-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="369fb-106">Alternativ kann dies vermieden werden, indem das <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>-Element nach dem Aufruf von <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName> explizit neu ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="369fb-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="369fb-107">name</span><span class="sxs-lookup"><span data-stu-id="369fb-107">Name</span></span>    | <span data-ttu-id="369fb-108">Wert</span><span class="sxs-lookup"><span data-stu-id="369fb-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="369fb-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="369fb-109">Scope</span></span>   |<span data-ttu-id="369fb-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="369fb-110">Edge</span></span>|
|<span data-ttu-id="369fb-111">Version</span><span class="sxs-lookup"><span data-stu-id="369fb-111">Version</span></span>|<span data-ttu-id="369fb-112">4.5</span><span class="sxs-lookup"><span data-stu-id="369fb-112">4.5</span></span>|
|<span data-ttu-id="369fb-113">Typ</span><span class="sxs-lookup"><span data-stu-id="369fb-113">Type</span></span>|<span data-ttu-id="369fb-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="369fb-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="369fb-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="369fb-115">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
