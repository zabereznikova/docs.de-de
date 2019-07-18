---
ms.openlocfilehash: 51691ced3f05201f784ccdeffbc130e34748b7c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379695"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>WPF DataTemplate-Elemente sind jetzt für die UIA sichtbar

|   |   |
|---|---|
|Details|In der Vergangenheit waren <xref:System.Windows.DataTemplate?displayProperty=name>-Elemente für die Benutzeroberflächenautomatisierung nicht sichtbar. Ab Version 4.5 erkennt die Benutzeroberflächenautomatisierung diese Elemente. Dies ist zwar in vielen Fällen hilfreich, kann aber bei Tests zu Problemen führen, die von UIA-Strukturen abhängen, die keine <xref:System.Windows.DataTemplate?displayProperty=name>-Elemente enthalten.|
|Vorschlag|Tests für die Benutzeroberflächenautomatisierung für diese App müssen möglicherweise aktualisiert werden, um die UIA-Struktur zu berücksichtigen, die jetzt zuvor unsichtbare <xref:System.Windows.DataTemplate?displayProperty=name>-Elemente enthält. Beispielsweise müssen Tests, die erwarten, dass einige Elemente nebeneinander angeordnet sind, jetzt möglicherweise davon ausgehen, dass sich zwischen diesen Elementen zuvor unsichtbare UIA-Elemente befinden. Möglicherweise müssen auch Tests mit neuen Werten aktualisiert werden, die auf bestimmte Werte oder Indizes für UIA-Elemente angewiesen sind.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.DataTemplate.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)?displayProperty=nameWithType></li></ul>|
