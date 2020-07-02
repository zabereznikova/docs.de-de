---
ms.openlocfilehash: 6d804dd335cb18d5febc2ca5f794af92963bece1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620495"
---
### <a name="right-clicking-on-a-wpf-datagrid-row-header-changes-the-datagrid-selection"></a><span data-ttu-id="860ef-101">Bei einem Rechtsklick auf einen Zeilenheader des WPF-DataGrid-Steuerelements wird die DataGrid-Auswahl geändert</span><span class="sxs-lookup"><span data-stu-id="860ef-101">Right clicking on a WPF DataGrid row header changes the DataGrid selection</span></span>

#### <a name="details"></a><span data-ttu-id="860ef-102">Details</span><span class="sxs-lookup"><span data-stu-id="860ef-102">Details</span></span>

<span data-ttu-id="860ef-103">Bei einem Rechtsklick auf einen ausgewählten <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>-Zeilenheader, wird nur diese ausgewählte Zeile geändert, wenn in <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> mehrere Zeilen ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="860ef-103">Right-clicking a selected <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> row header while multiple rows are selected results in the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s selection changing to only that row.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="860ef-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="860ef-104">Suggestion</span></span>

<span data-ttu-id="860ef-105">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="860ef-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="860ef-106">name</span><span class="sxs-lookup"><span data-stu-id="860ef-106">Name</span></span>    | <span data-ttu-id="860ef-107">Wert</span><span class="sxs-lookup"><span data-stu-id="860ef-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="860ef-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="860ef-108">Scope</span></span>   |<span data-ttu-id="860ef-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="860ef-109">Edge</span></span>|
|<span data-ttu-id="860ef-110">Version</span><span class="sxs-lookup"><span data-stu-id="860ef-110">Version</span></span>|<span data-ttu-id="860ef-111">4.5</span><span class="sxs-lookup"><span data-stu-id="860ef-111">4.5</span></span>|
|<span data-ttu-id="860ef-112">Typ</span><span class="sxs-lookup"><span data-stu-id="860ef-112">Type</span></span>|<span data-ttu-id="860ef-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="860ef-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="860ef-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="860ef-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.%23ctor></li></ul>|
