---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379668"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="1ed4d-101">In einem WPF-TextBox-Element markierter Text wird in einer anderen Farbe angezeigt, wenn das Textfeld inaktiv ist</span><span class="sxs-lookup"><span data-stu-id="1ed4d-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1ed4d-102">Details</span><span class="sxs-lookup"><span data-stu-id="1ed4d-102">Details</span></span>|<span data-ttu-id="1ed4d-103">Wenn in .NET Framework 4.5 ein WPF-Textfeldsteuerelement inaktiv ist (nicht den Eingabefokus hat), wird der im Feld markierte Text in einer anderen Farbe als bei einem aktiven Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ed4d-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="1ed4d-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1ed4d-104">Suggestion</span></span>|<span data-ttu-id="1ed4d-105">Das vorherige Verhalten (.NET Framework 4.0) kann wiederhergestellt werden, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported>-Eigenschaft auf <code>false</code> festlegen.</span><span class="sxs-lookup"><span data-stu-id="1ed4d-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="1ed4d-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="1ed4d-106">Scope</span></span>|<span data-ttu-id="1ed4d-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1ed4d-107">Edge</span></span>|
|<span data-ttu-id="1ed4d-108">Version</span><span class="sxs-lookup"><span data-stu-id="1ed4d-108">Version</span></span>|<span data-ttu-id="1ed4d-109">4.5</span><span class="sxs-lookup"><span data-stu-id="1ed4d-109">4.5</span></span>|
|<span data-ttu-id="1ed4d-110">Typ</span><span class="sxs-lookup"><span data-stu-id="1ed4d-110">Type</span></span>|<span data-ttu-id="1ed4d-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1ed4d-111">Runtime</span></span>|
|<span data-ttu-id="1ed4d-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1ed4d-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
