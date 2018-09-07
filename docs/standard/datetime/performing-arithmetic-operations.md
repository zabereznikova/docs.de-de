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
ms.openlocfilehash: c2a50823b812541786cf1bebfd6b1262ce2e9314
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44064016"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>Durchführen arithmetischer Datums- und Uhrzeitoperationen

Obwohl sowohl die <xref:System.DateTime> und <xref:System.DateTimeOffset> Strukturen Member bieten, die arithmetische Operationen für ihre Werte durchführen, die Ergebnisse der arithmetischen Operationen sind sehr verschieden. In diesem Thema werden diese Unterschiede untersucht, bezieht sich diese auf Grad von Zeitzonen in Datums-und Uhrzeitdaten und erläutert, wie voll Zeitzone bewusst Operationen mit Datums-und Uhrzeitdaten.

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>Vergleiche und arithmetische Operationen mit DateTime-Werten

Die <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschaft ermöglicht eine <xref:System.DateTimeKind> Wert zugewiesen werden soll, um das Datum und die Uhrzeit an, ob es sich um Ortszeit, koordinierter Weltzeit (UTC) oder die Zeit in einer nicht spezifizierten Zeitzone darstellt. Diese eingeschränkten Zeitzoneninformationen werden jedoch ignoriert, wenn vergleichen oder Durchführen von Datums- und uhrzeitberechnungen auf <xref:System.DateTimeKind> Werte. Dies wird im folgenden Beispiel veranschaulicht, in dem die aktuelle lokale Zeit mit der aktuellen UTC-Zeit verglichen wird.

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

Die <xref:System.DateTime.CompareTo%28System.DateTime%29> Methode meldet, dass die Ortszeit früher als (oder kleiner als) die UTC-Zeit und der Subtraktionsvorgang gibt an, dass die Differenz zwischen UTC und der lokalen Zeit für ein System in den USA Pacific Standard Time sieben Stunden beträgt. Da diese beiden Werte verschiedene Darstellungen eines einzigen Zeitpunkts angeben, ist das Zeitintervall in diesem Fall vollständig auf die Abweichung der Ortszeit von UTC zurückzuführen.

Allgemeiner ausgedrückt, die <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> Eigenschaft wirkt sich nicht auf die von der zurückgegebenen Ergebnisse <xref:System.DateTime.Kind> -Vergleich und arithmetische Methoden (wie der Vergleich zweier identischer Zeitpunkte zeigt), aber die Interpretation dieser Ergebnisse beeinflussen können. Zum Beispiel:

* Das Ergebnis einer beliebigen arithmetischen Operation für zwei Werte für Datum und Uhrzeit ausgeführt, deren <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> -Eigenschaften beide den Wert <xref:System.DateTimeKind> gibt das tatsächliche Zeitintervall zwischen den beiden Werten wieder. Entsprechend gibt der Vergleich zweier solcher Datums- und Zeitwerte genau die Beziehung zwischen den Zeiten wieder.

* Das Ergebnis einer arithmetischen oder Vergleichsoperation für zwei Werte für Datum und Uhrzeit ausgeführt, deren <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> -Eigenschaften beide den Wert <xref:System.DateTimeKind> oder für zwei Datums- / Werte mit unterschiedlichen <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> -Eigenschaftswerten gibt den Zeitunterschied zwischen den beiden Werten.

* Bei arithmetischen oder Vergleichsoperationen für lokale Datums- und Uhrzeitwerte wird nicht berücksichtigt, ob ein bestimmter Wert mehrdeutig oder ungültig ist. Ebenso wenig werden die Auswirkungen von Anpassungsregeln berücksichtigt, die sich aus dem Übergang der lokalen Zeitzone zu oder von der Sommerzeit ergeben.

* Jeder Vorgang, bei dem die Differenz zwischen UTC und einer lokalen Zeit verglichen oder berechnet wird, umfasst im Ergebnis ein Zeitintervall, das der Abweichung der lokalen Zeitzone von UTC entspricht.

* Jeder Vorgang, bei dem die Differenz zwischen einer nicht spezifizierten Uhrzeit und UTC oder der Ortszeit verglichen oder berechnet wird, gibt die einfache Uhrzeit wieder. Zeitzonenunterschiede werden nicht berücksichtigt, und das Ergebnis gibt nicht die Anwendung der Regeln zur Zeitzonenanpassung wieder.

* Jeder Vorgang, bei dem die Differenz zwischen zwei nicht spezifizierten Zeiten verglichen oder berechnet wird, kann ein unbekanntes Intervall umfassen, das den Unterschied zwischen den Zeiten in zwei verschiedenen Zeitzonen wiedergibt.

Es gibt viele Szenarien, in welcher Zeitzone Unterschiede haben keine Auswirkungen auf Datums- und uhrzeitberechnungen (eine Erläuterung der einige dieser, finden Sie unter [auswählen zwischen DateTime, DateTimeOffset, TimeSpan und TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)) oder in dem Kontext von Datum und Uhrzeit definiert Daten die Bedeutung von Vergleichs- oder arithmetischen Operationen.

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>Vergleiche und arithmetische Operationen mit DateTimeOffset-Werten

Ein <xref:System.DateTimeOffset> Wert enthält, nicht nur ein Datum und eine Uhrzeit, sondern auch einem Offset, der das Datum und Uhrzeit relativ zur UTC eindeutig definiert. Dadurch wird es möglich, eine Übereinstimmung anders als für <xref:System.DateTimeOffset> Werte. Während <xref:System.DateTime> Werte sind gleich, wenn sie denselben Datums- und Uhrzeitwert <xref:System.DateTimeOffset> Werte sind gleich, wenn beide auf demselben Zeitpunkt beziehen. Dadurch wird eine <xref:System.DateTimeOffset> -Wert genauer und erfordert weniger Interpretationsaufwand, bei der Verwendung in vergleichen sowie in den meisten arithmetischen Operationen, die das Intervall zwischen zwei Datumsangaben und Uhrzeiten zu bestimmen. Das folgende Beispiel, das ist die <xref:System.DateTimeOffset> mit dem vorherigen Beispiel, das lokale verglichen und UTC <xref:System.DateTimeOffset> Werte, die dieser Unterschied im Verhalten veranschaulicht.

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

In diesem Beispiel die <xref:System.DateTimeOffset.CompareTo%2A> Methode gibt an, dass die aktuelle lokale Zeit und die aktuelle UTC-Zeit identisch sind, und Subtraktion von <xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)> Werte gibt an, dass der Unterschied zwischen den beiden Zeiten <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.

Die wichtigste Einschränkung bei der Verwendung von <xref:System.DateTimeOffset> Werte in Datums- und Uhrzeitoperationen ist, obwohl <xref:System.DateTimeOffset> Werte haben einige Zeitzonen, jedoch nicht vollständig Zeitzone beachten. Obwohl die <xref:System.DateTimeOffset> -Wertoffset gibt ein Zeitzonenoffset von der UTC wieder bei einer <xref:System.DateTimeOffset> Variablen zunächst ein Wert zugewiesen wird, es wird getrennt von der Zeitzone danach. Da er nicht mehr direkt einer identifizierbaren Zeit zugeordnet ist, werden bei der Addition und Subtraktion von Datums- und Uhrzeitintervallen keine Regeln zur Zeitzonenanpassung berücksichtigt.

Zur Veranschaulichung: Der Übergang zur Sommerzeit erfolgt in der US-Zeitzone Central Standard Time um 2:00 Uhr morgens am 9. März 2008. Demnach sollten sich durch das Hinzufügen eines Intervalls von 2,5 Stunden zur Central Standard Time um 1:30 Uhr am 9. März 2008 ein Datum und eine Uhrzeit von 5:00 Uhr morgens am 9. März 2008 ergeben. Wie das folgende Beispiel zeigt, ist das Ergebnis der Addition jedoch 4:00 Uhr morgens am 9. März 2008. Beachten Sie, dass das Ergebnis dieses Vorgangs den richtigen Zeitpunkt darstellt, auch wenn es sich nicht um die Uhrzeit in der Zeitzone handelt, an der wir interessiert sind (d.h. sie weist nicht die erwartete Zeitzonenabweichung auf).

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>Arithmetische Operationen mit Uhrzeiten in Zeitzonen

Die <xref:System.TimeZoneInfo> Klasse umfasst eine Reihe von Methoden für die Konvertierung, die Anpassungen automatisch anwenden, wenn sie Zeiten von einer Zeitzone in einen anderen konvertieren. Hierzu gehört Folgendes:

* Die <xref:System.TimeZoneInfo.ConvertTime%2A> und <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A> -Methoden, die Zeiten zwischen zwei beliebigen Zeitzonen konvertieren.

* Die <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> und <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> -Methoden, die die Zeit in einer bestimmten Zeitzone in UTC konvertieren, oder Konvertieren der UTC in die Zeit in einer bestimmten Zeitzone.

Weitere Informationen finden Sie unter [Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md).

Die <xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)> -Klasse bietet keine Methoden, die automatisch Anwenden von Anpassungsregeln beim Ausführen von arithmetischen Datums- und Uhrzeitoperationen. Sie können zu diesem Zweck jedoch die Uhrzeit einer Zeitzone in UTC konvertieren, die arithmetische Operation durchführen und die Uhrzeit dann wieder in die Zeit der Zeitzone zurückkonvertieren. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).

Beispielsweise ähnelt der folgende Code dem vorherigen Code, bei dem 2,5 Stunden zu 2:00 Uhr am 9. März 2008 hinzugefügt wurden. Da jedoch vor dem Ausführen von Datums- und Uhrzeitoperationen die Central Standard Time in UTC konvertiert und das Ergebnis dann von UTC zurück in Central Standard Time zurückkonvertiert wird, gibt die Ergebniszeit den Übergang von der Zeitzone Central Standard Time zur Sommerzeit wieder.

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>Siehe auch

* [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
* [Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)
