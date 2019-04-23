---
ms.openlocfilehash: addfd55fd01b13e9088e4706ff846fc624aafa68
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804062"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>PreviewLostKeyboardFocus wird wiederholt aufgerufen, wenn der Handler ein Windows Forms-Meldungsfeld anzeigt

|   |   |
|---|---|
|Details|Ab .NET Framework 4.5 führt der Aufruf von <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> über einen <xref:System.Windows.UIElement.PreviewLostKeyboardFocus>-Handler dazu, dass der Handler erneut auslöst, wenn das Meldungsfeld geschlossen wird, was ggf. zu einer Endlosschleife von Meldungsfeldern führt.|
|Vorschlag|Es gibt zwei Optionen, um dieses Problem zu umgehen:<ol><li>Es kann durch Aufrufen von <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> anstelle von <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> vermieden werden.</li><li>Es kann durch Anzeigen des Meldungsfelds über einen <xref:System.Windows.UIElement.LostKeyboardFocus?displayProperty=nameWithType>-Ereignishandler (im Gegensatz zu einem <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=name>-Ereignishandler) vermieden werden.</li></ol>|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
