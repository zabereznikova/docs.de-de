---
ms.openlocfilehash: 972601874d80d82ebae8b79779acfed82e5570cb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497885"
---
### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a><span data-ttu-id="c12e9-101">Das Aufrufen von Items.Refresh für die WPF-Steuerelemente ListBox, ListView oder DataGrid mit ausgewählten Einträgen kann dazu führen, dass im Element doppelte Einträge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c12e9-101">Calling Items.Refresh on a WPF ListBox, ListView, or DataGrid with items selected can cause duplicate items to appear in the element</span></span>

#### <a name="details"></a><span data-ttu-id="c12e9-102">Details</span><span class="sxs-lookup"><span data-stu-id="c12e9-102">Details</span></span>

<span data-ttu-id="c12e9-103">In .NET Framework 4.5 kann der Aufruf von „ListBox.Items.Refresh“ mit ausgewählten Einträgen über Code dazu führen, dass die in <xref:System.Windows.Controls.ListBox?displayProperty=fullName> ausgewählten Einträge in der Liste doppelt vorkommen.</span><span class="sxs-lookup"><span data-stu-id="c12e9-103">In the .NET Framework 4.5, calling ListBox.Items.Refresh from code while items are selected in a <xref:System.Windows.Controls.ListBox?displayProperty=fullName> can cause the selected items to be duplicated in the list.</span></span> <span data-ttu-id="c12e9-104">Bei <xref:System.Windows.Controls.ListView?displayProperty=fullName> und <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> tritt ein ähnliches Problem auf.</span><span class="sxs-lookup"><span data-stu-id="c12e9-104">A similar issue occurs with <xref:System.Windows.Controls.ListView?displayProperty=fullName> and <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span></span> <span data-ttu-id="c12e9-105">Dieses Problem wurde in .NET Framework 4.6 behoben.</span><span class="sxs-lookup"><span data-stu-id="c12e9-105">This is fixed in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c12e9-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c12e9-106">Suggestion</span></span>

<span data-ttu-id="c12e9-107">Dieses Problem kann dadurch umgangen werden, dass die Auswahl der Einträge programmgesteuert aufgehoben wird, bevor <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> aufgerufen wird. Nachdem der Aufruf abgeschlossen ist, werden die Einträge erneut ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="c12e9-107">This issue may be worked around by programmatically unselecting items before <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=fullName> is called and then re-selecting them after the call is completed.</span></span> <span data-ttu-id="c12e9-108">Dieses Problem wurde alternativ in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="c12e9-108">Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="c12e9-109">name</span><span class="sxs-lookup"><span data-stu-id="c12e9-109">Name</span></span>    | <span data-ttu-id="c12e9-110">Wert</span><span class="sxs-lookup"><span data-stu-id="c12e9-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c12e9-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="c12e9-111">Scope</span></span>   |<span data-ttu-id="c12e9-112">Gering</span><span class="sxs-lookup"><span data-stu-id="c12e9-112">Minor</span></span>|
|<span data-ttu-id="c12e9-113">Version</span><span class="sxs-lookup"><span data-stu-id="c12e9-113">Version</span></span>|<span data-ttu-id="c12e9-114">4.5</span><span class="sxs-lookup"><span data-stu-id="c12e9-114">4.5</span></span>|
|<span data-ttu-id="c12e9-115">Typ</span><span class="sxs-lookup"><span data-stu-id="c12e9-115">Type</span></span>|<span data-ttu-id="c12e9-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c12e9-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c12e9-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c12e9-117">Affected APIs</span></span>

- <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Data.CollectionView.Refresh`

-->
