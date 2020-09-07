---
ms.openlocfilehash: 9d960774161fc44810f90ca30f56eb98f98de3ff
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497589"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="811d1-101">WPF TextBox verwendet standardmäßig 100 als Grenzwert für die Aktion „Rückgängig machen“</span><span class="sxs-lookup"><span data-stu-id="811d1-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="811d1-102">Details</span><span class="sxs-lookup"><span data-stu-id="811d1-102">Details</span></span>

<span data-ttu-id="811d1-103">In .NET Framework 4.5 beträgt der Standardgrenzwert für ein WPF-Textfeld 100 (im Gegensatz zu .NET Framework 4.0, bei dem der Wert unbegrenzt ist).</span><span class="sxs-lookup"><span data-stu-id="811d1-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="811d1-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="811d1-104">Suggestion</span></span>

<span data-ttu-id="811d1-105">Wenn der Grenzwert von 100 für die Aktion „Rückgängig machen“ zu niedrig ist, kann er explizit mit <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="811d1-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="811d1-106">name</span><span class="sxs-lookup"><span data-stu-id="811d1-106">Name</span></span>    | <span data-ttu-id="811d1-107">Wert</span><span class="sxs-lookup"><span data-stu-id="811d1-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="811d1-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="811d1-108">Scope</span></span>   |<span data-ttu-id="811d1-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="811d1-109">Edge</span></span>|
|<span data-ttu-id="811d1-110">Version</span><span class="sxs-lookup"><span data-stu-id="811d1-110">Version</span></span>|<span data-ttu-id="811d1-111">4.5</span><span class="sxs-lookup"><span data-stu-id="811d1-111">4.5</span></span>|
|<span data-ttu-id="811d1-112">Typ</span><span class="sxs-lookup"><span data-stu-id="811d1-112">Type</span></span>|<span data-ttu-id="811d1-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="811d1-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="811d1-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="811d1-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
