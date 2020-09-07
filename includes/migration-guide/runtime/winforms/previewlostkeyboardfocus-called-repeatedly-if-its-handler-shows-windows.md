---
ms.openlocfilehash: c4a3d903894027a01d32ca132d1233da9d9c3ee5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496834"
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
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.ContentElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.IInputElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement.PreviewLostKeyboardFocus?displayProperty=nameWithType>
- <xref:System.Windows.UIElement3D.PreviewLostKeyboardFocus?displayProperty=nameWithType>

<!--

#### Affected APIs

- `E:System.Windows.ContentElement.PreviewLostKeyboardFocus`
- `E:System.Windows.IInputElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement.PreviewLostKeyboardFocus`
- `E:System.Windows.UIElement3D.PreviewLostKeyboardFocus`

-->
