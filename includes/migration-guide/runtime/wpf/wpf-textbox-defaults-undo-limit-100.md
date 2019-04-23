---
ms.openlocfilehash: de79182e326082786c1e0691f8888e30cd410f5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235222"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="f276c-101">WPF TextBox verwendet standardmäßig 100 als Grenzwert für die Aktion „Rückgängig machen“</span><span class="sxs-lookup"><span data-stu-id="f276c-101">WPF TextBox defaults to undo limit of 100</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f276c-102">Details</span><span class="sxs-lookup"><span data-stu-id="f276c-102">Details</span></span>|<span data-ttu-id="f276c-103">In .NET Framework 4.5 beträgt der Standardgrenzwert für ein WPF-Textfeld 100 (im Gegensatz zu .NET Framework 4.0, bei dem der Wert unbegrenzt ist).</span><span class="sxs-lookup"><span data-stu-id="f276c-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>|
|<span data-ttu-id="f276c-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="f276c-104">Suggestion</span></span>|<span data-ttu-id="f276c-105">Wenn der Grenzwert von 100 für die Aktion „Rückgängig machen“ zu niedrig ist, kann er explizit festgelegt werden mit</span><span class="sxs-lookup"><span data-stu-id="f276c-105">If an undo limit of 100 is too low, the limit can be set explicitly with</span></span> <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit>|
|<span data-ttu-id="f276c-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="f276c-106">Scope</span></span>|<span data-ttu-id="f276c-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f276c-107">Edge</span></span>|
|<span data-ttu-id="f276c-108">Version</span><span class="sxs-lookup"><span data-stu-id="f276c-108">Version</span></span>|<span data-ttu-id="f276c-109">4.5</span><span class="sxs-lookup"><span data-stu-id="f276c-109">4.5</span></span>|
|<span data-ttu-id="f276c-110">Typ</span><span class="sxs-lookup"><span data-stu-id="f276c-110">Type</span></span>|<span data-ttu-id="f276c-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f276c-111">Runtime</span></span>|
|<span data-ttu-id="f276c-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f276c-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
