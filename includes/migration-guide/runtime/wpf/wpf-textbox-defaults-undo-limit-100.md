---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620483"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="1ce5d-101">WPF TextBox verwendet standardmäßig 100 als Grenzwert für die Aktion „Rückgängig machen“</span><span class="sxs-lookup"><span data-stu-id="1ce5d-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="1ce5d-102">Details</span><span class="sxs-lookup"><span data-stu-id="1ce5d-102">Details</span></span>

<span data-ttu-id="1ce5d-103">In .NET Framework 4.5 beträgt der Standardgrenzwert für ein WPF-Textfeld 100 (im Gegensatz zu .NET Framework 4.0, bei dem der Wert unbegrenzt ist).</span><span class="sxs-lookup"><span data-stu-id="1ce5d-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1ce5d-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1ce5d-104">Suggestion</span></span>

<span data-ttu-id="1ce5d-105">Wenn der Grenzwert von 100 für die Aktion „Rückgängig machen“ zu niedrig ist, kann er explizit mit <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1ce5d-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="1ce5d-106">name</span><span class="sxs-lookup"><span data-stu-id="1ce5d-106">Name</span></span>    | <span data-ttu-id="1ce5d-107">Wert</span><span class="sxs-lookup"><span data-stu-id="1ce5d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1ce5d-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="1ce5d-108">Scope</span></span>   |<span data-ttu-id="1ce5d-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1ce5d-109">Edge</span></span>|
|<span data-ttu-id="1ce5d-110">Version</span><span class="sxs-lookup"><span data-stu-id="1ce5d-110">Version</span></span>|<span data-ttu-id="1ce5d-111">4.5</span><span class="sxs-lookup"><span data-stu-id="1ce5d-111">4.5</span></span>|
|<span data-ttu-id="1ce5d-112">Typ</span><span class="sxs-lookup"><span data-stu-id="1ce5d-112">Type</span></span>|<span data-ttu-id="1ce5d-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1ce5d-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1ce5d-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1ce5d-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
