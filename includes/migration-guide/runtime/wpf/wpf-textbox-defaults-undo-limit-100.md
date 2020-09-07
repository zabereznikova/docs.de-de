---
ms.openlocfilehash: 9d960774161fc44810f90ca30f56eb98f98de3ff
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497589"
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
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
