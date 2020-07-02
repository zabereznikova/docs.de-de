---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620472"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>WPF DataTemplate-Elemente sind jetzt für die UIA sichtbar

#### <a name="details"></a>Details

In der Vergangenheit waren <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente für die Benutzeroberflächenautomatisierung nicht sichtbar. Ab Version 4.5 erkennt die Benutzeroberflächenautomatisierung diese Elemente. Dies ist zwar in vielen Fällen hilfreich, kann aber bei Tests zu Problemen führen, die von UIA-Strukturen abhängen, die keine <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente enthalten.

#### <a name="suggestion"></a>Vorschlag

Tests für die Benutzeroberflächenautomatisierung für diese App müssen möglicherweise aktualisiert werden, um die UIA-Struktur zu berücksichtigen, die jetzt zuvor unsichtbare <xref:System.Windows.DataTemplate?displayProperty=fullName>-Elemente enthält. Beispielsweise müssen Tests, die erwarten, dass einige Elemente nebeneinander angeordnet sind, jetzt möglicherweise davon ausgehen, dass sich zwischen diesen Elementen zuvor unsichtbare UIA-Elemente befinden. Möglicherweise müssen auch Tests mit neuen Werten aktualisiert werden, die auf bestimmte Werte oder Indizes für UIA-Elemente angewiesen sind.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
