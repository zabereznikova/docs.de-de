---
title: Durchführen arithmetischer Datums- und Uhrzeitoperationen
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], arithmetic operations
- dates [.NET Framework], arithmetic operations
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
ms.openlocfilehash: 0db0331620da8337930bfacf5d1bbd9913647afa
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344176"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Durchführen arithmetischer Datums- und Uhrzeitoperationen

Obwohl sowohl <xref:System.DateTime> die <xref:System.DateTimeOffset> als auch die Strukturen Member bereitstellen, die arithmetische Operationen für ihre Werte ausführen, sind die Ergebnisse von arithmetischen Operationen sehr unterschiedlich. In diesem Thema werden diese Unterschiede untersucht, sie mit graduierenden Zeitzonenbewusstseins in Datums- und Uhrzeitdaten verknüpft und erläutert, wie vollständig zeitzonenbewusste Vorgänge mithilfe von Datums- und Uhrzeitdaten ausgeführt werden können.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Vergleiche und arithmetische Operationen mit DateTime-Werten

Die <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschaft <xref:System.DateTimeKind> ermöglicht es, dem Datum und der Uhrzeit einen Wert zuzuweisen, um anzugeben, ob er die Ortszeit, die koordinierte Weltzeit (UTC) oder die Zeit in einer nicht angegebenen Zeitzone darstellt. Diese begrenzten Zeitzoneninformationen werden jedoch ignoriert, wenn Sie die <xref:System.DateTimeKind> Datums- und Uhrzeitarithmetik für Werte vergleichen oder ausführen. Dies wird im folgenden Beispiel veranschaulicht, in dem die aktuelle lokale Zeit mit der aktuellen UTC-Zeit verglichen wird.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Die <xref:System.DateTime.CompareTo%28System.DateTime%29> Methode meldet, dass die Ortszeit vor (oder weniger als) der UTC-Zeit liegt, und der Subtraktionsvorgang gibt an, dass der Unterschied zwischen UTC und der ortszeit für ein System in der Standardzeitzone des US-Pazifiks sieben Stunden beträgt. Da diese beiden Werte jedoch unterschiedliche Darstellungen eines einzelnen Zeitpunkts bieten, ist in diesem Fall klar, dass das Zeitintervall vollständig dem Offset der lokalen Zeitzone von UTC zuzurechnen ist.

Im Allgemeinen <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> wirkt sich die Eigenschaft <xref:System.DateTime.Kind> nicht auf die Ergebnisse aus, die durch Vergleichs- und arithmetische Methoden zurückgegeben werden (wie der Vergleich zweier identischer Zeitpunkte zeigt), obwohl sie die Interpretation dieser Ergebnisse beeinflussen kann. Zum Beispiel:

- Das Ergebnis einer arithmetischen Operation, die an <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> zwei <xref:System.DateTimeKind> Datums- und Uhrzeitwerten ausgeführt wird, deren Eigenschaften beide gleich sind, spiegelt das tatsächliche Zeitintervall zwischen den beiden Werten wider. Entsprechend gibt der Vergleich zweier solcher Datums- und Zeitwerte genau die Beziehung zwischen den Zeiten wieder.

- Das Ergebnis eines arithmetischen oder Vergleichsvorgangs, <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> der auf <xref:System.DateTimeKind> zwei Datums- und <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Uhrzeitwerten ausgeführt wird, deren Eigenschaften sowohl gleich als auch auf zwei Datums- und Uhrzeitwerten mit unterschiedlichen Eigenschaftswerten sind, spiegelt die Differenz der Uhrzeit zwischen den beiden Werten wider.

- Bei arithmetischen oder Vergleichsoperationen für lokale Datums- und Uhrzeitwerte wird nicht berücksichtigt, ob ein bestimmter Wert mehrdeutig oder ungültig ist. Ebenso wenig werden die Auswirkungen von Anpassungsregeln berücksichtigt, die sich aus dem Übergang der lokalen Zeitzone zu oder von der Sommerzeit ergeben.

- Jeder Vorgang, bei dem die Differenz zwischen UTC und einer lokalen Zeit verglichen oder berechnet wird, umfasst im Ergebnis ein Zeitintervall, das der Abweichung der lokalen Zeitzone von UTC entspricht.

- Jeder Vorgang, bei dem die Differenz zwischen einer nicht spezifizierten Uhrzeit und UTC oder der Ortszeit verglichen oder berechnet wird, gibt die einfache Uhrzeit wieder. Zeitzonenunterschiede werden nicht berücksichtigt, und das Ergebnis gibt nicht die Anwendung der Regeln zur Zeitzonenanpassung wieder.

- Jeder Vorgang, bei dem die Differenz zwischen zwei nicht spezifizierten Zeiten verglichen oder berechnet wird, kann ein unbekanntes Intervall umfassen, das den Unterschied zwischen den Zeiten in zwei verschiedenen Zeitzonen wiedergibt.

Es gibt viele Szenarien, in denen Zeitzonenunterschiede sich nicht auf Datums- und Uhrzeitberechnungen auswirken (für eine Diskussion einiger dieser Szenarien finden Sie unter [Auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) oder in denen der Kontext der Datums- und Uhrzeitdaten die Bedeutung von Vergleichs- oder Arithmetikvorgängen definiert.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Vergleiche und arithmetische Operationen mit DateTimeOffset-Werten

Ein <xref:System.DateTimeOffset> Wert enthält nicht nur ein Datum und eine Uhrzeit, sondern auch einen Offset, der dieses Datum und die Uhrzeit im Verhältnis zu UTC eindeutig definiert. Dadurch ist es möglich, Gleichheit <xref:System.DateTimeOffset> etwas anders zu definieren als für Werte. Während <xref:System.DateTime> Werte gleich sind, wenn sie den <xref:System.DateTimeOffset> gleichen Datums- und Uhrzeitwert haben, sind Werte gleich, wenn sie beide auf denselben Zeitpunkt verweisen. Dies <xref:System.DateTimeOffset> macht einen Wert genauer und weniger interpretierbar, wenn er in Vergleichen und in den meisten arithmetischen Operationen verwendet wird, die das Intervall zwischen zwei Datums- und Uhrzeitangaben bestimmen. Das folgende Beispiel, <xref:System.DateTimeOffset> das dem vorherigen Beispiel entspricht, <xref:System.DateTimeOffset> in dem lokale und UTC-Werte verglichen wurden, veranschaulicht diesen Verhaltensunterschied.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In diesem Beispiel <xref:System.DateTimeOffset.CompareTo%2A> gibt die Methode an, dass die aktuelle Ortszeit und <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> die aktuelle UTC-Zeit gleich <xref:System.TimeSpan.Zero?displayProperty=nameWithType>sind, und die Subtraktion von Werten gibt an, dass die Differenz zwischen den beiden Zeiten ist .

Die Hauptbeschränkung <xref:System.DateTimeOffset> für die Verwendung von Werten in <xref:System.DateTimeOffset> der Datums- und Uhrzeitarithmetik besteht darin, dass Werte zwar eine gewisse Zeitzonen-Bewusstheit aufweisen, aber nicht vollständig Zeitzonen-bewusst sind. Obwohl <xref:System.DateTimeOffset> der Offset des Werts den Offset einer Zeitzone von UTC widerspiegelt, wenn einer <xref:System.DateTimeOffset> Variablen zuerst ein Wert zugewiesen wird, wird er danach von der Zeitzone getrennt. Da er nicht mehr direkt einer identifizierbaren Zeit zugeordnet ist, werden bei der Addition und Subtraktion von Datums- und Uhrzeitintervallen keine Regeln zur Zeitzonenanpassung berücksichtigt.

Zur Veranschaulichung erfolgt der Übergang zur Sommerzeit in der zentralen Standardzeitzone der USA um 2:00 Uhr. am 9. März 2008 hinzugefügt wurden. Demnach sollten sich durch das Hinzufügen eines Intervalls von 2,5 Stunden zur Central Standard Time um 1:30 Uhr am 9. März 2008 ein Datum und eine Uhrzeit von 5:00 Uhr morgens am 9. März 2008 hinzugefügt wurden. Wie das folgende Beispiel zeigt, ist das Ergebnis der Addition jedoch 4:00 Uhr morgens am 9. März 2008 hinzugefügt wurden. Beachten Sie, dass das Ergebnis dieses Vorgangs den richtigen Zeitpunkt darstellt, obwohl es nicht die Zeit in der Zeitzone ist, an der wir interessiert sind (d. h., es hat nicht den erwarteten Zeitzonenversatz).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Arithmetische Operationen mit Zeiten in Zeitzonen

Die <xref:System.TimeZoneInfo> Klasse enthält eine Reihe von Konvertierungsmethoden, die automatisch Anpassungen anwenden, wenn sie Zeiten von einer Zeitzone in eine andere konvertieren. Dabei handelt es sich z. B. um:

- Die <xref:System.TimeZoneInfo.ConvertTime%2A> <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> und Methoden, die Zeiten zwischen zwei beliebigen Zeitzonen konvertieren.

- Die <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> und Methoden, die die Zeit in einer bestimmten Zeitzone in UTC konvertieren oder UTC in die Zeit in einer bestimmten Zeitzone konvertieren.

Weitere Informationen finden Sie unter [Konvertieren von Zeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md).

Die <xref:System.TimeZoneInfo> Klasse stellt keine Methoden bereit, die beim Ausführen der Datums- und Uhrzeitarithmetik automatisch Anpassungsregeln anwenden. Sie können zu diesem Zweck jedoch die Uhrzeit einer Zeitzone in UTC konvertieren, die arithmetische Operation durchführen und die Uhrzeit dann wieder in die Zeit der Zeitzone zurückkonvertieren. Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von Zeitzonen in der Datums- und Uhrzeitarithmetik](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).

Beispielsweise ähnelt der folgende Code dem vorherigen Code, bei dem 2,5 Stunden zu 2:00 Uhr am 9. März 2008 hinzugefügt wurden. Da jedoch vor dem Ausführen von Datums- und Uhrzeitoperationen die Central Standard Time in UTC konvertiert und das Ergebnis dann von UTC zurück in Central Standard Time zurückkonvertiert wird, gibt die Ergebniszeit den Übergang von der Zeitzone Central Standard Time zur Sommerzeit wieder.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
