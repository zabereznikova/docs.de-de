---
ms.openlocfilehash: 2aa6603e2ed77ffa94fbc6325cd5db50985bda6a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620413"
---
### <a name="previewlostkeyboardfocus-is-called-repeatedly-if-its-handler-shows-a-windows-forms-message-box"></a>PreviewLostKeyboardFocus wird wiederholt aufgerufen, wenn der Handler ein Windows Forms-Meldungsfeld anzeigt

#### <a name="details"></a>Details

Ab .NET Framework 4.5 führt der Aufruf von <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> über einen <xref:System.Windows.UIElement.PreviewLostKeyboardFocus>-Handler dazu, dass der Handler erneut auslöst, wenn das Meldungsfeld geschlossen wird, was ggf. zu einer Endlosschleife von Meldungsfeldern führt.

#### <a name="suggestion"></a>Vorschlag

Es gibt zwei Optionen, um dieses Problem zu umgehen:<ol><li>Es kann durch Aufrufen von <xref:System.Windows.MessageBox.Show%2A?displayProperty=nameWithType> anstelle von <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=nameWithType> vermieden werden.</li><li>Es kann durch Anzeigen des Meldungsfelds über einen <xref:System.Windows.UIElement.LostKeyboardFocus>-Ereignishandler (im Gegensatz zu einem <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=fullName>-Ereignishandler) vermieden werden.</li></ol>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType></li><li><xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType></li></ul>|
