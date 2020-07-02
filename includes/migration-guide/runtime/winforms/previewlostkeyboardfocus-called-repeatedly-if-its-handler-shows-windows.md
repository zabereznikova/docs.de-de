---
ms.openlocfilehash: 2aa6603e2ed77ffa94fbc6325cd5db50985bda6a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620413"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a><span data-ttu-id="6d937-101">PreviewLostKeyboardFocus wird wiederholt aufgerufen, wenn der Handler ein Windows Forms-Meldungsfeld anzeigt</span><span class="sxs-lookup"><span data-stu-id="6d937-101">PreviewLostKeyboardFocus is called repeatedly if its handler shows a Windows Forms message box</span></span>

#### <a name="details"></a><span data-ttu-id="6d937-102">Details</span><span class="sxs-lookup"><span data-stu-id="6d937-102">Details</span></span>

<span data-ttu-id="6d937-103">Ab .NET Framework 4.5 führt der Aufruf von <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> über einen <xref:System.Windows.UIElement.PreviewLostKeyboardFocus>-Handler dazu, dass der Handler erneut auslöst, wenn das Meldungsfeld geschlossen wird, was ggf. zu einer Endlosschleife von Meldungsfeldern führt.</span><span class="sxs-lookup"><span data-stu-id="6d937-103">Beginning in the .NET Framework 4.5, calling <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> from a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus> handler will cause the handler to re-fire when the message box is closed, potentially resulting in an infinite loop of message boxes.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6d937-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6d937-104">Suggestion</span></span>

<span data-ttu-id="6d937-105">Es gibt zwei Optionen, um dieses Problem zu umgehen:</span><span class="sxs-lookup"><span data-stu-id="6d937-105">There are two options to work around this issue:</span></span><ol><li><span data-ttu-id="6d937-106">Es kann durch Aufrufen von <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> anstelle von <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="6d937-106">It may be avoided by calling <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> instead of <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType>.</span></span></li><li><span data-ttu-id="6d937-107">Es kann durch Anzeigen des Meldungsfelds über einen <xref:System.Windows.UIElement.LostKeyboardFocus>-Ereignishandler (im Gegensatz zu einem <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>-Ereignishandler) vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="6d937-107">It may be avoided by showing the message box from a <xref:System.Windows.UIElement.LostKeyboardFocus> event handler (as opposed to a <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName> event handler).</span></span></li></ol>

| <span data-ttu-id="6d937-108">name</span><span class="sxs-lookup"><span data-stu-id="6d937-108">Name</span></span>    | <span data-ttu-id="6d937-109">Wert</span><span class="sxs-lookup"><span data-stu-id="6d937-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6d937-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="6d937-110">Scope</span></span>   |<span data-ttu-id="6d937-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6d937-111">Edge</span></span>|
|<span data-ttu-id="6d937-112">Version</span><span class="sxs-lookup"><span data-stu-id="6d937-112">Version</span></span>|<span data-ttu-id="6d937-113">4.5</span><span class="sxs-lookup"><span data-stu-id="6d937-113">4.5</span></span>|
|<span data-ttu-id="6d937-114">Typ</span><span class="sxs-lookup"><span data-stu-id="6d937-114">Type</span></span>|<span data-ttu-id="6d937-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6d937-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6d937-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6d937-116">Affected APIs</span></span>

-<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
