---
ms.openlocfilehash: de79182e326082786c1e0691f8888e30cd410f5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235222"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>WPF TextBox verwendet standardmäßig 100 als Grenzwert für die Aktion „Rückgängig machen“

|   |   |
|---|---|
|Details|In .NET Framework 4.5 beträgt der Standardgrenzwert für ein WPF-Textfeld 100 (im Gegensatz zu .NET Framework 4.0, bei dem der Wert unbegrenzt ist).|
|Vorschlag|Wenn der Grenzwert von 100 für die Aktion „Rückgängig machen“ zu niedrig ist, kann er explizit mit <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> festgelegt werden.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
