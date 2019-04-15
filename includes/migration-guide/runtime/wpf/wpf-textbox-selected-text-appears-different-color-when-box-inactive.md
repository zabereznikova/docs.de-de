---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235759"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a>In einem WPF-TextBox-Element markierter Text wird in einer anderen Farbe angezeigt, wenn das Textfeld inaktiv ist

|   |   |
|---|---|
|Details|Wenn in .NET Framework 4.5 ein WPF-Textfeldsteuerelement inaktiv ist (nicht den Eingabefokus hat), wird der im Feld markierte Text in einer anderen Farbe als bei einem aktiven Steuerelement angezeigt.|
|Vorschlag|Das vorherige Verhalten (.NET Framework 4.0) kann wiederhergestellt werden, indem Sie die <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported>-Eigenschaft auf <code>false</code> festlegen.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
