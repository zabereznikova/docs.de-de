---
ms.openlocfilehash: c01705002ad87a12389078d75ffd0f91f934d36e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496701"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>In einem WPF-TextBox-Element markierter Text wird in einer anderen Farbe angezeigt, wenn das Textfeld inaktiv ist

#### <a name="details"></a>Details

Wenn in .NET Framework 4.5 ein WPF-Textfeldsteuerelement inaktiv ist (nicht den Eingabefokus hat), wird der im Feld markierte Text in einer anderen Farbe als bei einem aktiven Steuerelement angezeigt.

#### <a name="suggestion"></a>Vorschlag

Das vorherige Verhalten (.NET Framework 4.0) kann wiederhergestellt werden, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported>-Eigenschaft auf <code>false</code> festlegen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
