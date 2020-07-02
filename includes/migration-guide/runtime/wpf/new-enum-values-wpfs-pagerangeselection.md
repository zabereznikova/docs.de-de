---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620459"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="a1ee5-101">Neue Enumerationswerte in der PageRangeSelection-Enumeration für WPF</span><span class="sxs-lookup"><span data-stu-id="a1ee5-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="a1ee5-102">Details</span><span class="sxs-lookup"><span data-stu-id="a1ee5-102">Details</span></span>

<span data-ttu-id="a1ee5-103">Es wurden zwei neue Member (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> und <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) zur <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>-Enumeration hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a1ee5-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a1ee5-104">Suggestion</span></span>

<span data-ttu-id="a1ee5-105">In den meisten Fällen wirken sich diese Änderungen nicht auf Benutzercode aus.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="a1ee5-106">Code, der von einer bestimmten Anzahl von Elementen abhängig ist, die in <xref:System.Enum.GetNames(System.Type)>- oder <xref:System.Enum.GetValues(System.Type)>-Aufrufen für den <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>-Typ vorhanden sind, sollte jedoch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a1ee5-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="a1ee5-107">name</span><span class="sxs-lookup"><span data-stu-id="a1ee5-107">Name</span></span>    | <span data-ttu-id="a1ee5-108">Wert</span><span class="sxs-lookup"><span data-stu-id="a1ee5-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a1ee5-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="a1ee5-109">Scope</span></span>   |<span data-ttu-id="a1ee5-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a1ee5-110">Edge</span></span>|
|<span data-ttu-id="a1ee5-111">Version</span><span class="sxs-lookup"><span data-stu-id="a1ee5-111">Version</span></span>|<span data-ttu-id="a1ee5-112">4.5</span><span class="sxs-lookup"><span data-stu-id="a1ee5-112">4.5</span></span>|
|<span data-ttu-id="a1ee5-113">Typ</span><span class="sxs-lookup"><span data-stu-id="a1ee5-113">Type</span></span>|<span data-ttu-id="a1ee5-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a1ee5-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a1ee5-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a1ee5-115">Affected APIs</span></span>

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
