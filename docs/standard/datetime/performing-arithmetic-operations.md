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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01314c160fc531f5c97a1369c8444dce7f590d53
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106615"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Durchführen arithmetischer Datums- und Uhrzeitoperationen

Obwohl sowohl die <xref:System.DateTime> -als <xref:System.DateTimeOffset> auch die-Struktur Member bereitstellen, die arithmetische Operationen für ihre Werte durchführen, sind die Ergebnisse der arithmetischen Operationen sehr unterschiedlich. In diesem Thema werden diese Unterschiede untersucht, Sie werden mit dem Grad der Zeitzoneninformationen in Datums-und uhrzeitanfrage verknüpft, und es wird erläutert, wie Sie mithilfe von Datums-und Uhrzeitdaten voll Zeit Zonen

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Vergleiche und arithmetische Operationen mit DateTime-Werten

Mit <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> der-Eigenschaft <xref:System.DateTimeKind> kann dem Datum und der Uhrzeit ein Wert zugewiesen werden, um anzugeben, ob er die Ortszeit, die koordinierte Weltzeit (UTC) oder die Zeit in einer nicht angegebenen Zeitzone darstellt. Diese begrenzten Zeitzoneninformationen werden jedoch beim Vergleichen oder Durchführen von Datums-und Uhrzeit Arithmetik für <xref:System.DateTimeKind> Werte ignoriert. Dies wird im folgenden Beispiel veranschaulicht, in dem die aktuelle lokale Zeit mit der aktuellen UTC-Zeit verglichen wird.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Die <xref:System.DateTime.CompareTo%28System.DateTime%29> -Methode meldet, dass die Ortszeit früher als (oder kleiner als) die UTC-Zeit ist, und der Subtraktions Vorgang gibt an, dass der Unterschied zwischen UTC und der Ortszeit für ein System in der Pacific Standard Time sieben Stunden beträgt. Da diese beiden Werte verschiedene Darstellungen eines einzigen Zeitpunkts angeben, ist das Zeitintervall in diesem Fall vollständig auf die Abweichung der Ortszeit von UTC zurückzuführen.

Im Allgemeinen wirkt sich <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> die-Eigenschaft nicht auf die Ergebnisse aus <xref:System.DateTime.Kind> , die durch Vergleichs-und arithmetische Methoden zurückgegeben werden (wie der Vergleich zweier identischer Zeitpunkte anzeigt), obwohl dies die Interpretation dieser Ergebnisse beeinflussen kann. Beispiel:

- Das Ergebnis einer beliebigen arithmetischen Operation für zwei Datums-und Uhrzeitwerte, <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> deren <xref:System.DateTimeKind> Eigenschaften beide das tatsächliche Zeitintervall zwischen den beiden Werten widerspiegeln. Entsprechend gibt der Vergleich zweier solcher Datums- und Zeitwerte genau die Beziehung zwischen den Zeiten wieder.

- Das Ergebnis einer beliebigen arithmetischen oder Vergleichsoperation für zwei Datums-und Uhrzeitwerte, <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> deren <xref:System.DateTimeKind> Eigenschaften gleich oder bei zwei Datums-und Uhrzeitwerten mit verschiedenen <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschafts Werten den Unterschied in der Uhrzeitangabe widerspiegeln. zwischen den beiden Werten.

- Bei arithmetischen oder Vergleichsoperationen für lokale Datums- und Uhrzeitwerte wird nicht berücksichtigt, ob ein bestimmter Wert mehrdeutig oder ungültig ist. Ebenso wenig werden die Auswirkungen von Anpassungsregeln berücksichtigt, die sich aus dem Übergang der lokalen Zeitzone zu oder von der Sommerzeit ergeben.

- Jeder Vorgang, bei dem die Differenz zwischen UTC und einer lokalen Zeit verglichen oder berechnet wird, umfasst im Ergebnis ein Zeitintervall, das der Abweichung der lokalen Zeitzone von UTC entspricht.

- Jeder Vorgang, bei dem die Differenz zwischen einer nicht spezifizierten Uhrzeit und UTC oder der Ortszeit verglichen oder berechnet wird, gibt die einfache Uhrzeit wieder. Zeitzonenunterschiede werden nicht berücksichtigt, und das Ergebnis gibt nicht die Anwendung der Regeln zur Zeitzonenanpassung wieder.

- Jeder Vorgang, bei dem die Differenz zwischen zwei nicht spezifizierten Zeiten verglichen oder berechnet wird, kann ein unbekanntes Intervall umfassen, das den Unterschied zwischen den Zeiten in zwei verschiedenen Zeitzonen wiedergibt.

Es gibt viele Szenarios, in denen Zeitzonenunterschiede sich nicht auf Datums-und Uhrzeit Berechnungen auswirken (eine Erläuterung einiger dieser Informationen finden Sie unter [auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) oder in dem der Kontext der Datums-und Uhrzeitdaten definiert die Bedeutung von Vergleichs-oder arithmetischen Vorgängen.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Vergleiche und arithmetische Operationen mit DateTimeOffset-Werten

Ein <xref:System.DateTimeOffset> -Wert enthält nicht nur ein Datum und eine Uhrzeit, sondern auch einen Offset, der das Datum und die Uhrzeit relativ zur UTC eindeutig definiert. Dadurch ist es möglich, Gleichheit etwas anders zu definieren als <xref:System.DateTimeOffset> bei Werten. Während <xref:System.DateTime> Werte gleich sind, wenn Sie denselben Datums-und Uhrzeitwert <xref:System.DateTimeOffset> aufweisen, sind die Werte gleich, wenn beide auf denselben Zeitpunkt verweisen. Dadurch wird ein <xref:System.DateTimeOffset> Wert präziser und weniger interpretiert, wenn er in vergleichen und in den meisten arithmetischen Operationen verwendet wird, die das Intervall zwischen zwei Datums-und Uhrzeiten bestimmen. Das folgende Beispiel, das dem <xref:System.DateTimeOffset> vorherigen Beispiel entspricht, das die lokalen Werte und die UTC <xref:System.DateTimeOffset> -Werte verglichen hat, veranschaulicht diesen Unterschied im Verhalten.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In diesem Beispiel gibt die <xref:System.DateTimeOffset.CompareTo%2A> -Methode an, dass die aktuelle Ortszeit und die aktuelle UTC-zeitgleich sind, und die <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> Subtraktion von-Werten gibt an, dass der <xref:System.TimeSpan.Zero?displayProperty=nameWithType>Unterschied zwischen den beiden Zeiten ist.

Die wichtigste Einschränkung bei der <xref:System.DateTimeOffset> Verwendung von Werten in arithmetischen Datums-und <xref:System.DateTimeOffset> Uhrzeit Werten besteht darin, dass die Werte für ein gewisses Zeit Zonen Bewusstsein sind, aber Sie sind nicht voll Zeit Zonen fähig. Obwohl der <xref:System.DateTimeOffset> Offset des Werts einen Zeit Zonen Offset von UTC widerspiegelt, wenn <xref:System.DateTimeOffset> eine Variable erstmalig einem Wert zugewiesen wird, wird Sie später von der Zeitzone getrennt. Da er nicht mehr direkt einer identifizierbaren Zeit zugeordnet ist, werden bei der Addition und Subtraktion von Datums- und Uhrzeitintervallen keine Regeln zur Zeitzonenanpassung berücksichtigt.

Zur Veranschaulichung: Der Übergang zur Sommerzeit erfolgt in der US-Zeitzone Central Standard Time um 2:00 Uhr morgens am 9. März 2008. Demnach sollten sich durch das Hinzufügen eines Intervalls von 2,5 Stunden zur Central Standard Time um 1:30 Uhr am 9. März 2008 ein Datum und eine Uhrzeit von 5:00 Uhr morgens am 9. März 2008 ergeben. Wie das folgende Beispiel zeigt, ist das Ergebnis der Addition jedoch 4:00 Uhr morgens am 9. März 2008. Beachten Sie, dass das Ergebnis dieses Vorgangs den richtigen Zeitpunkt darstellt, auch wenn es sich nicht um die Uhrzeit in der Zeitzone handelt, an der wir interessiert sind (d.h. sie weist nicht die erwartete Zeitzonenabweichung auf).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Arithmetische Operationen mit Uhrzeiten in Zeitzonen

Die <xref:System.TimeZoneInfo> -Klasse enthält eine Reihe von Konvertierungs Methoden, die automatisch Anpassungen anwenden, wenn Sie Zeiten von einer Zeitzone in eine andere konvertieren. Hierzu gehört Folgendes:

- Die <xref:System.TimeZoneInfo.ConvertTime%2A> - <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> Methode und die-Methode, die Zeiten zwischen zwei beliebigen Zeitzonen konvertieren.

- Die <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> - <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> Methode und die-Methode, die die Uhrzeit in einer bestimmten Zeitzone in UTC konvertieren, oder die UTC in die Uhrzeit in einer bestimmten Zeitzone konvertieren.

Weitere Informationen finden Sie unter [umstellen von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md).

Die <xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> -Klasse stellt keine Methoden bereit, die automatisch Anpassungsregeln anwenden, wenn Sie arithmetische Datums-und Uhrzeit Operationen durchführen. Sie können zu diesem Zweck jedoch die Uhrzeit einer Zeitzone in UTC konvertieren, die arithmetische Operation durchführen und die Uhrzeit dann wieder in die Zeit der Zeitzone zurückkonvertieren. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie Zeitzonen in arithmetischen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)Datums-und Uhrzeit Operationen.

Beispielsweise ähnelt der folgende Code dem vorherigen Code, bei dem 2,5 Stunden zu 2:00 Uhr am 9. März 2008 hinzugefügt wurden. Da jedoch vor dem Ausführen von Datums- und Uhrzeitoperationen die Central Standard Time in UTC konvertiert und das Ergebnis dann von UTC zurück in Central Standard Time zurückkonvertiert wird, gibt die Ergebniszeit den Übergang von der Zeitzone Central Standard Time zur Sommerzeit wieder.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums-und Uhrzeit Operationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
