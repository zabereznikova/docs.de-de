---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620483"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>WPF TextBox verwendet standardmäßig 100 als Grenzwert für die Aktion „Rückgängig machen“

#### <a name="details"></a>Details

In .NET Framework 4.5 beträgt der Standardgrenzwert für ein WPF-Textfeld 100 (im Gegensatz zu .NET Framework 4.0, bei dem der Wert unbegrenzt ist).

#### <a name="suggestion"></a>Vorschlag

Wenn der Grenzwert von 100 für die Aktion „Rückgängig machen“ zu niedrig ist, kann er explizit mit <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> festgelegt werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
