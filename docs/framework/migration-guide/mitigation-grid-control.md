---
title: "Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes
- .NET Framework 4.7 retargeting changes
- WPF retargeting changes
- Grid control retargeting changes
ms.assetid: 707c064d-85e9-4ea1-aefb-e42b60b88679
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54391538ac0b2daf307cba2f7ceff1984d26b0ce
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-grid-control39s-space-allocation-to-star-columns"></a>Entschärfung: Platzzuweisung an mit Stern gekennzeichnete Spalten durch das Rastersteuerelement

Bei Anwendungen mit .NET Framework 4.7 und höher als Zielplattform ersetzt WPF den Algorithmus, den das <xref:System.Windows.Controls.Grid>-Steuerelement verwendet, um Platz für \*-Spalten zuzuweisen. 

## <a name="whats-changed"></a>Neues

Der neue Algorithmus behebt mehrere Probleme, die beim alten Algorithmus auftreten:

1. Die Gesamtzuweisung an Spalten kann die Breite des Rasters überschreiten. Dies kann beim Zuweisen von Platz an eine Spalte geschehen, deren proportionaler Anteil geringer als ihre Mindestgröße ist. Der Algorithmus weist die Mindestgröße zu, wodurch der für andere Spalten verfügbare Platz verringert wird. Wenn keine zuzuweisenden \*-Spalten mehr vorhanden sind, ist die Gesamtzuweisung zu groß.

1. Die Gesamtzuweisung kann die Breite des Rasters unterschreiten. Dies ist das umgekehrte Problem zu Nr. 1, das beim Zuweisen zu einer Spalte auftritt, deren proportionaler Anteil größer als ihre Maximalgröße ist, wenn keine \*-Spalten zum Ausgleich des Über- oder Untermaßes vorhanden sind.

1. Zwei \*-Spalten können Zuweisungen erhalten, die nicht proportional zu ihren -Gewichtungen sind. Dies ist eine mildere Version von Nr. 1/Nr. 2, die beim Zuweisen zu den *-Spalten A, B und C (in dieser Reihenfolge) auftritt, wobei der proportionale Anteil von B gegen deren Min- oder Max-Bedingung verstößt. Wie oben ändert sich dadurch der für Spalte C zur Verfügung stehende Platz, die proportional eine kleinere (oder größeren) Zuweisung als A erhält.

1. Spalten mit extrem hohen Gewichtungen (> 10^298) werden alle behandelt, als ob sie die Gewichtung 10^298 aufwiesen. Proportionale Unterschiede zwischen ihnen (und zwischen Spalten mit erheblich kleineren Gewichtungen) werden nicht berücksichtigt.

1. Spalten mit der Gewichtung unendlich werden nicht ordnungsgemäß behandelt. [Tatsächlich lässt sich die Gewichtung nicht auf unendlich festlegen, aber das ist eine künstliche Einschränkung. Der Zuweisungscode hat versucht, das Problem zu behandeln, dabei aber versagt.]

1. Mehrere kleinere Probleme beim Vermeiden von Überlauf, Unterlauf, Genauigkeitsverlust und ähnlichen Gleitkommaproblemen.

1. Anpassungen für Layoutglättung sind bei ausreichend hohem DPI fehlerhaft.

Der neue Algorithmus erzeugt Ergebnisse, die den folgenden Kriterien genügen:

A. Die einer *-Spalte zugewiesene Breite ist niemals kleiner als ihre Mindestbreite oder größer als ihre Maximalbreite.

B. Jede -Spalte, der nicht ihre Mindest- oder Maximalbreite zugewiesen wird, wird eine Breite zugewiesen, die proportional zu ihrer -Gewichtung ist. Genauer gesagt, wenn zwei Spalten die Breite x bzw. y zugewiesen werden und keine der beiden Spalten ihre Minimal- oder Maximalbreite erhält, stehen die den Spalten zugewiesenen tatsächlichen Breiten v und w im gleichen Verhältnis: v / w == x / y.

C. Die Gesamtbreite, die den „proportionalen“ \*-Spalten zugewiesen wird, entspricht dem verfügbaren Platz nach der Zuweisung an die Spalten, die Bedingungen unterliegen (feste Spalten, Spalten mit automatischer Breite und \*-Spalten, denen die Minimal- oder Maximalbreite zugewiesen wird). Diese kann Null sein, beispielsweise, wenn die Summe der Mindestbreiten die zur Verfügung stehende Breite des Rasters überschreitet.

D. Alle diese Anweisungen müssen im Hinblick auf das „ideale“ Layout interpretiert werden. Wenn Layoutglättung aktiviert ist, können die tatsächlichen Breiten um bis zu ein Pixel von den idealen Breiten abweichen.

Der alte Algorithmus berücksichtigte in den oben dargestellten Fällen (A), nicht jedoch die anderen Kriterien.

Alle Aussagen über Spalten und Breite in diesem Thema gelten ebenso für Zeilen und Höhe.

## <a name="impact"></a>Auswirkungen

Der neue Algorithmus ändert die den \*-Spalten zugewiesene tatsächliche Breite in einer Reihe von Fällen:

- Wenn eine oder mehrere \*-Spalten außerdem eine Minimal- oder Maximalbreite aufweisen, die die proportionale Zuweisung für die betreffende Spalte außer Kraft setzt. (Die Minimalbreite kann aus einer expliziten <xref:System.Windows.FrameworkElement.MinWidth%2A>-Deklaration oder aus einem impliziten Minimalwert abgeleitet werden, der sich aus dem Spalteninhalt ergibt. Die maximale Breite kann nur explizit aus einer <xref:System.Windows.FrameworkElement.MaxWidth%2A>-Deklaration definiert werden.)

- Wenn eine oder mehrere \*-Spalten eine extrem große \*-Gewichtung deklarieren, größer als 10^298.

- Wenn die \*-Gewichtungen ausreichend verschieden sind, um zu Gleitkommainstabilität zu führen (Überlauf, Unterlauf, Genauigkeitsverlust).

- Wenn Layoutglättung aktiviert ist und der effektive DPI-Wert der Anzeige ausreichend hoch ist.

In den beiden ersten Fällen können sich die vom neuen Algorithmus erzeugten Breiten erheblich von den durch den alten Algorithmus erzeugten unterscheiden; im letzten Fall beträgt der Unterschied höchstens ein oder zwei Pixel.

## <a name="mitigation"></a>Problemumgehung

Standardmäßig verwenden Apps mit einer .NET Framework-Zielplattform ab .NET Framework 4.7 den neuen Algorithmus, während Apps mit der Zielplattform .NET Framework 4.6.2 oder früher den alten Algorithmus verwenden.

Um die Standardeinstellung außer Kraft zu setzen, verwenden Sie die folgenden Konfigurationseinstellung:

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true" /> 
</runtime>
```

Der Wert „true“ legt den alten Algorithmus fest, „false“ den neuen.

## <a name="see-also"></a>Siehe auch
[Änderungen der Neuzuweisungen in .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

