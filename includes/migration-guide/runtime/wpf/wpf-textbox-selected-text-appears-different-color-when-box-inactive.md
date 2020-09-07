---
ms.openlocfilehash: c01705002ad87a12389078d75ffd0f91f934d36e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496701"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="bd7db-101">In einem WPF-TextBox-Element markierter Text wird in einer anderen Farbe angezeigt, wenn das Textfeld inaktiv ist</span><span class="sxs-lookup"><span data-stu-id="bd7db-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="bd7db-102">Details</span><span class="sxs-lookup"><span data-stu-id="bd7db-102">Details</span></span>

<span data-ttu-id="bd7db-103">Wenn in .NET Framework 4.5 ein WPF-Textfeldsteuerelement inaktiv ist (nicht den Eingabefokus hat), wird der im Feld markierte Text in einer anderen Farbe als bei einem aktiven Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd7db-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bd7db-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="bd7db-104">Suggestion</span></span>

<span data-ttu-id="bd7db-105">Das vorherige Verhalten (.NET Framework 4.0) kann wiederhergestellt werden, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported>-Eigenschaft auf <code>false</code> festlegen.</span><span class="sxs-lookup"><span data-stu-id="bd7db-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="bd7db-106">name</span><span class="sxs-lookup"><span data-stu-id="bd7db-106">Name</span></span>    | <span data-ttu-id="bd7db-107">Wert</span><span class="sxs-lookup"><span data-stu-id="bd7db-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bd7db-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="bd7db-108">Scope</span></span>   |<span data-ttu-id="bd7db-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bd7db-109">Edge</span></span>|
|<span data-ttu-id="bd7db-110">Version</span><span class="sxs-lookup"><span data-stu-id="bd7db-110">Version</span></span>|<span data-ttu-id="bd7db-111">4.5</span><span class="sxs-lookup"><span data-stu-id="bd7db-111">4.5</span></span>|
|<span data-ttu-id="bd7db-112">Typ</span><span class="sxs-lookup"><span data-stu-id="bd7db-112">Type</span></span>|<span data-ttu-id="bd7db-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="bd7db-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="bd7db-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="bd7db-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
