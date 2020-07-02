---
ms.openlocfilehash: cd59818fe674e10a206725bea8a74c4aceed99b1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620471"
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
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
