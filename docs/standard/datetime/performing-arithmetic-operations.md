---
title: Durchführen arithmetischer Datums- und Uhrzeitoperationen
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET], arithmetic operations
- dates [.NET], arithmetic operations
- time zones [.NET], arithmetic operations
- arithmetic operations [.NET], dates and times
- dates [.NET], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
ms.openlocfilehash: af294c45359f6226c4189aabb34fdfc670bbd1c9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817769"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Durchführen arithmetischer Datums- und Uhrzeitoperationen

Obwohl sowohl die <xref:System.DateTime> -als auch die- <xref:System.DateTimeOffset> Struktur Member bereitstellen, die arithmetische Operationen für ihre Werte durchführen, sind die Ergebnisse der arithmetischen Operationen sehr unterschiedlich. In diesem Thema werden diese Unterschiede untersucht, Sie werden mit dem Grad der Zeitzoneninformationen in Datums-und uhrzeitanfrage verknüpft, und es wird erläutert, wie Sie mithilfe von Datums-und Uhrzeitdaten voll Zeit Zonen

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Vergleiche und arithmetische Operationen mit DateTime-Werten

Mit der- <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschaft kann <xref:System.DateTimeKind> dem Datum und der Uhrzeit ein Wert zugewiesen werden, um anzugeben, ob er die Ortszeit, die koordinierte Weltzeit (UTC) oder die Zeit in einer nicht angegebenen Zeitzone darstellt. Diese begrenzten Zeitzoneninformationen werden jedoch beim Vergleichen oder Durchführen von Datums-und Uhrzeit Arithmetik für <xref:System.DateTimeKind> Werte ignoriert. Dies wird im folgenden Beispiel veranschaulicht, in dem die aktuelle lokale Zeit mit der aktuellen UTC-Zeit verglichen wird.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Die <xref:System.DateTime.CompareTo%28System.DateTime%29> -Methode meldet, dass die Ortszeit älter als (oder kleiner als) die UTC-Zeit ist, und der Subtraktions Vorgang gibt an, dass der Unterschied zwischen UTC und der Ortszeit für ein System in der US Pacific Standard-Zeitzone sieben Stunden beträgt. Da diese beiden Werte jedoch unterschiedliche Darstellungen eines einzelnen Zeitpunkts bereitstellen, ist es in diesem Fall klar, dass das Zeitintervall vollständig auf die Abweichung der lokalen Zeitzone von UTC zurückzuführen ist.

Im Allgemeinen wirkt sich die <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> -Eigenschaft nicht auf die Ergebnisse aus, die durch <xref:System.DateTime.Kind> Vergleichs-und arithmetische Methoden zurückgegeben werden (wie der Vergleich zweier identischer Zeitpunkte anzeigt), obwohl dies die Interpretation dieser Ergebnisse beeinflussen kann. Beispiel:

- Das Ergebnis einer beliebigen arithmetischen Operation für zwei Datums-und Uhrzeitwerte, deren <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschaften beide <xref:System.DateTimeKind> das tatsächliche Zeitintervall zwischen den beiden Werten widerspiegeln. Entsprechend gibt der Vergleich zweier solcher Datums- und Zeitwerte genau die Beziehung zwischen den Zeiten wieder.

- Das Ergebnis einer arithmetischen oder Vergleichsoperation für zwei Datums-und Uhrzeitwerte, deren <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschaften gleich <xref:System.DateTimeKind> oder zwei Datums-und Uhrzeitwerten mit unterschiedlichen <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschafts Werten sind, gibt den Unterschied in der Uhrzeitangabe zwischen den beiden Werten wieder.

- Bei arithmetischen oder Vergleichsoperationen für lokale Datums- und Uhrzeitwerte wird nicht berücksichtigt, ob ein bestimmter Wert mehrdeutig oder ungültig ist. Ebenso wenig werden die Auswirkungen von Anpassungsregeln berücksichtigt, die sich aus dem Übergang der lokalen Zeitzone zu oder von der Sommerzeit ergeben.

- Jeder Vorgang, bei dem die Differenz zwischen UTC und einer lokalen Zeit verglichen oder berechnet wird, umfasst im Ergebnis ein Zeitintervall, das der Abweichung der lokalen Zeitzone von UTC entspricht.

- Jeder Vorgang, bei dem die Differenz zwischen einer nicht spezifizierten Uhrzeit und UTC oder der Ortszeit verglichen oder berechnet wird, gibt die einfache Uhrzeit wieder. Zeitzonenunterschiede werden nicht berücksichtigt, und das Ergebnis gibt nicht die Anwendung der Regeln zur Zeitzonenanpassung wieder.

- Jeder Vorgang, bei dem die Differenz zwischen zwei nicht spezifizierten Zeiten verglichen oder berechnet wird, kann ein unbekanntes Intervall umfassen, das den Unterschied zwischen den Zeiten in zwei verschiedenen Zeitzonen wiedergibt.

Es gibt viele Szenarien, in denen Zeitzonenunterschiede sich nicht auf Datums-und Uhrzeit Berechnungen auswirken. (eine Erläuterung einiger dieser Informationen finden Sie unter [auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](choosing-between-datetime.md)) oder in dem der Kontext der Datums-und Uhrzeit Daten die Bedeutung von Vergleichs-oder arithmetischen Vorgängen definiert.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Vergleiche und arithmetische Operationen mit DateTimeOffset-Werten

Ein- <xref:System.DateTimeOffset> Wert enthält nicht nur ein Datum und eine Uhrzeit, sondern auch einen Offset, der das Datum und die Uhrzeit relativ zur UTC eindeutig definiert. Dadurch ist es möglich, Gleichheit etwas anders zu definieren als bei <xref:System.DateTimeOffset> Werten. Während <xref:System.DateTime> Werte gleich sind, wenn Sie denselben Datums-und Uhrzeitwert aufweisen, <xref:System.DateTimeOffset> sind die Werte gleich, wenn beide auf denselben Zeitpunkt verweisen. Dadurch wird ein <xref:System.DateTimeOffset> Wert präziser und weniger interpretiert, wenn er in vergleichen und in den meisten arithmetischen Operationen verwendet wird, die das Intervall zwischen zwei Datums-und Uhrzeiten bestimmen. Das folgende Beispiel, das dem <xref:System.DateTimeOffset> vorherigen Beispiel entspricht, das die lokalen Werte und die UTC- <xref:System.DateTimeOffset> Werte verglichen hat, veranschaulicht diesen Unterschied im Verhalten.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In diesem Beispiel gibt die <xref:System.DateTimeOffset.CompareTo%2A> -Methode an, dass die aktuelle Ortszeit und die aktuelle UTC-zeitgleich sind, und die Subtraktion von- <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> Werten gibt an, dass der Unterschied zwischen den beiden Zeiten ist <xref:System.TimeSpan.Zero?displayProperty=nameWithType> .

Die wichtigste Einschränkung bei der Verwendung von <xref:System.DateTimeOffset> Werten in arithmetischen Datums-und Uhrzeit Werten besteht darin, dass die <xref:System.DateTimeOffset> Werte für ein gewisses Zeit Zonen Bewusstsein sind, aber Sie sind nicht voll Zeit Zonen fähig. Obwohl der <xref:System.DateTimeOffset> Offset des Werts einen Zeit Zonen Offset von UTC widerspiegelt, wenn eine <xref:System.DateTimeOffset> Variable erstmalig einem Wert zugewiesen wird, wird Sie später von der Zeitzone getrennt. Da er nicht mehr direkt einer identifizierbaren Zeit zugeordnet ist, werden bei der Addition und Subtraktion von Datums- und Uhrzeitintervallen keine Regeln zur Zeitzonenanpassung berücksichtigt.

Um zu veranschaulichen, dass der Übergang zur Sommerzeit in der US-zentral Standard Zeitzone um 2:00 Uhr stattfindet. am 9. März 2008 hinzugefügt wurden. Demnach sollten sich durch das Hinzufügen eines Intervalls von 2,5 Stunden zur Central Standard Time um 1:30 Uhr am 9. März 2008 ein Datum und eine Uhrzeit von 5:00 Uhr morgens am 9. März 2008 hinzugefügt wurden. Wie das folgende Beispiel zeigt, ist das Ergebnis der Addition jedoch 4:00 Uhr morgens am 9. März 2008 hinzugefügt wurden. Beachten Sie, dass das Ergebnis dieses Vorgangs den richtigen Zeitpunkt darstellt, obwohl es sich nicht um die Zeit in der Zeitzone handelt, in der wir interessiert sind (d. h., Sie verfügt nicht über den erwarteten Zeit Zonen Offset).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Arithmetische Operationen mit Uhrzeiten in Zeitzonen

Die- <xref:System.TimeZoneInfo> Klasse enthält eine Reihe von Konvertierungs Methoden, die automatisch Anpassungen anwenden, wenn Sie Zeiten von einer Zeitzone in eine andere konvertieren. Hierzu gehört Folgendes:

- Die <xref:System.TimeZoneInfo.ConvertTime%2A> -Methode und die- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> Methode, die Zeiten zwischen zwei beliebigen Zeitzonen konvertieren.

- Die <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> -Methode und die- <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> Methode, die die Uhrzeit in einer bestimmten Zeitzone in UTC konvertieren, oder die UTC in die Uhrzeit in einer bestimmten Zeitzone konvertieren.

Weitere Informationen finden Sie unter [umstellen von Uhrzeiten zwischen Zeitzonen](converting-between-time-zones.md).

Die-Klasse stellt keine <xref:System.TimeZoneInfo> Methoden bereit, die automatisch Anpassungsregeln anwenden, wenn Sie arithmetische Datums-und Uhrzeit Operationen durchführen. Sie können zu diesem Zweck jedoch die Uhrzeit einer Zeitzone in UTC konvertieren, die arithmetische Operation durchführen und die Uhrzeit dann wieder in die Zeit der Zeitzone zurückkonvertieren. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von Zeitzonen in arithmetischen Datums-und Uhrzeit](use-time-zones-in-arithmetic.md)Operationen.

Beispielsweise ähnelt der folgende Code dem vorherigen Code, bei dem 2,5 Stunden zu 2:00 Uhr am 9. März 2008 hinzugefügt wurden. Da jedoch vor dem Ausführen von Datums- und Uhrzeitoperationen die Central Standard Time in UTC konvertiert und das Ergebnis dann von UTC zurück in Central Standard Time zurückkonvertiert wird, gibt die Ergebniszeit den Übergang von der Zeitzone Central Standard Time zur Sommerzeit wieder.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](use-time-zones-in-arithmetic.md)
