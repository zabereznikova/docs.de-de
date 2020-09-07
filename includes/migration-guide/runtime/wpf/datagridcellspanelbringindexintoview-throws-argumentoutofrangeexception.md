---
ms.openlocfilehash: 961ca545560a53fc2c1d52722b68ae460de66877
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497251"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="e5b5b-101">DataGridCellsPanel.BringIndexIntoView löst ArgumentOutOfRangeException aus</span><span class="sxs-lookup"><span data-stu-id="e5b5b-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

#### <a name="details"></a><span data-ttu-id="e5b5b-102">Details</span><span class="sxs-lookup"><span data-stu-id="e5b5b-102">Details</span></span>

<span data-ttu-id="e5b5b-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> wird asynchron ausgeführt, wenn die Spaltenvirtualisierung zwar aktiviert ist, die Spaltenbreiten aber noch nicht festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="e5b5b-104">Wenn Spalten entfernt werden, bevor der asynchrone Vorgang abgeschlossen ist, kann eine <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>-Ausnahme auftreten.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> can occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e5b5b-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e5b5b-105">Suggestion</span></span>

<span data-ttu-id="e5b5b-106">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e5b5b-106">Any one of the following:</span></span><ol><li><span data-ttu-id="e5b5b-107">Upgrade auf .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="e5b5b-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="e5b5b-108">Den neuesten Wartungspatch für .NET Framework 4.6.2 installieren</span><span class="sxs-lookup"><span data-stu-id="e5b5b-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="e5b5b-109">Entfernen Sie Spalten erst, wenn die asynchrone Antwort auf die <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>

| <span data-ttu-id="e5b5b-110">Name</span><span class="sxs-lookup"><span data-stu-id="e5b5b-110">Name</span></span>    | <span data-ttu-id="e5b5b-111">Wert</span><span class="sxs-lookup"><span data-stu-id="e5b5b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e5b5b-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="e5b5b-112">Scope</span></span>   |<span data-ttu-id="e5b5b-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e5b5b-113">Edge</span></span>|
|<span data-ttu-id="e5b5b-114">Version</span><span class="sxs-lookup"><span data-stu-id="e5b5b-114">Version</span></span>|<span data-ttu-id="e5b5b-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="e5b5b-115">4.6.2</span></span>|
|<span data-ttu-id="e5b5b-116">Typ</span><span class="sxs-lookup"><span data-stu-id="e5b5b-116">Type</span></span>|<span data-ttu-id="e5b5b-117">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e5b5b-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e5b5b-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e5b5b-118">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)`
- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)`

-->
