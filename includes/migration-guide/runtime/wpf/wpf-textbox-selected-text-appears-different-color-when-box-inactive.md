---
ms.openlocfilehash: cd59818fe674e10a206725bea8a74c4aceed99b1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620471"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="dceab-101">In einem WPF-TextBox-Element markierter Text wird in einer anderen Farbe angezeigt, wenn das Textfeld inaktiv ist</span><span class="sxs-lookup"><span data-stu-id="dceab-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="dceab-102">Details</span><span class="sxs-lookup"><span data-stu-id="dceab-102">Details</span></span>

<span data-ttu-id="dceab-103">Wenn in .NET Framework 4.5 ein WPF-Textfeldsteuerelement inaktiv ist (nicht den Eingabefokus hat), wird der im Feld markierte Text in einer anderen Farbe als bei einem aktiven Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dceab-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dceab-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="dceab-104">Suggestion</span></span>

<span data-ttu-id="dceab-105">Das vorherige Verhalten (.NET Framework 4.0) kann wiederhergestellt werden, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported>-Eigenschaft auf <code>false</code> festlegen.</span><span class="sxs-lookup"><span data-stu-id="dceab-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="dceab-106">name</span><span class="sxs-lookup"><span data-stu-id="dceab-106">Name</span></span>    | <span data-ttu-id="dceab-107">Wert</span><span class="sxs-lookup"><span data-stu-id="dceab-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dceab-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="dceab-108">Scope</span></span>   |<span data-ttu-id="dceab-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dceab-109">Edge</span></span>|
|<span data-ttu-id="dceab-110">Version</span><span class="sxs-lookup"><span data-stu-id="dceab-110">Version</span></span>|<span data-ttu-id="dceab-111">4.5</span><span class="sxs-lookup"><span data-stu-id="dceab-111">4.5</span></span>|
|<span data-ttu-id="dceab-112">Typ</span><span class="sxs-lookup"><span data-stu-id="dceab-112">Type</span></span>|<span data-ttu-id="dceab-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="dceab-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dceab-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="dceab-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
