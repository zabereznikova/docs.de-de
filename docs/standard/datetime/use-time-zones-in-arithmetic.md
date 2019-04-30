---
title: 'Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 053ca2d10deadf58d5bb8b4628fb5dee815d82c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026496"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen

Normalerweise beim Ausführen von Datum und Uhrzeit mithilfe von arithmetischen <xref:System.DateTime> oder <xref:System.DateTimeOffset> -Werten in den Ergebnissen berücksichtigt nicht die Anpassungsregeln der Zeitzone. Dies ist "true", auch wenn die Zeitzone des Datums-und Uhrzeit eindeutig erkennbar ist (z. B. wenn die <xref:System.DateTime.Kind%2A> -Eigenschaftensatz auf <xref:System.DateTimeKind.Local>). In diesem Thema wird gezeigt, wie Sie arithmetische Operationen für Datums-und Uhrzeitwerte durchführen, die zu einer bestimmten Zeitzone gehören. Die Ergebnisse der arithmetischen Operationen berücksichtigen die Anpassungsregeln der Zeitzone.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>So wenden Sie Anpassungsregeln auf arithmetische Datums- und Uhrzeitoperationen an

1. Implementieren Sie eine beliebige Methode, mit der ein Datums- und Uhrzeitwert eng mit der Zeitzone verknüpft wird, zu der er gehört. Deklarieren Sie z.B. eine Struktur, die sowohl den Datums- als auch den Uhrzeitwert und die Zeitzone einschließt. Im folgenden Beispiel wird dieser Ansatz zum Verknüpfen einer <xref:System.DateTime> Wert mit seiner Zeitzone.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Konvertiert eine Uhrzeit in Coordinated Universal Time (UTC) durch Aufrufen der <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> Methode oder der <xref:System.TimeZoneInfo.ConvertTime%2A> Methode.

3. Führen Sie die arithmetische Operation für die UTC-Zeit aus.

4. Konvertieren Sie die Zeit von UTC, der zugehörigen Zeitzone in der ursprünglichen Zeit durch Aufrufen der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> Methode.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Stunden und 30 Minuten zum 9. März 2008 um 1:30 Uhr Central Standard Time hinzugefügt. Die Umstellung auf Sommerzeit erfolgt in der Zeitzone dreißig Minuten später, um 2:00 Uhr am 9.März 2008. Da das Beispiel den vier Schritten folgt, die im vorherigen Abschnitt aufgeführt sind, ist das Ergebnis die richtige Zeit von 5:00 Uhr am 9. März 2008.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Beide <xref:System.DateTime> und <xref:System.DateTimeOffset> Werte werden an eine beliebige Zeitzone zu dem sie gehören möglicherweise aufgehoben. Um arithmetische Datums- und Uhrzeitoperationen so durchführen zu können, dass Anpassungsregeln für Zeitzonen automatisch angewendet werden, muss die Zeitzone, zu der der Datums- und Uhrzeitwert gehört, direkt identifizierbar sein. Dies bedeutet, dass Datum und Uhrzeit sowie die zugeordnete Zeitzone eng verknüpft sein müssen. Hierzu gibt es mehrere Möglichkeiten, darunter die folgenden:

* Nehmen Sie an, dass alle in einer Anwendung verwendeten Uhrzeiten zu einer bestimmten Zeitzone gehören. Obwohl dieser Ansatz in einigen Fällen geeignet ist, bietet er jedoch nur eingeschränkte Flexibilität sowie möglicherweise eine eingeschränkte Portabilität.

* Definieren Sie einen Typ, der ein Datum und eine Uhrzeit eng mit der zugehörigen Zeitzone verknüpft, indem Sie beide als Felder des Typs einschließen. Dieser Ansatz wird im Codebeispiel verwendet, in dem eine Struktur zum Speichern des Datums und der Uhrzeit sowie der Zeitzone in zwei Memberfeldern definiert wird.

Im Beispiel wird veranschaulicht, wie auf arithmetische Operationen <xref:System.DateTime> Werte, damit auf das Ergebnis die Anpassungsregeln der Zeitzone angewendet werden. Allerdings <xref:System.DateTimeOffset> Werte können genauso einfach verwendet werden. Das folgende Beispiel veranschaulicht, wie der Code in das ursprüngliche Beispiel angepasst werden möglicherweise <xref:System.DateTimeOffset> anstelle von <xref:System.DateTime> Werte.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Beachten Sie, dass diese Ergänzung einfach durchgeführt wird, auf die <xref:System.DateTimeOffset> Wert, ohne zuerst in UTC konvertiert, gibt das Ergebnis der richtige Zeitpunkt Zeitpunkt wieder, aber die Abweichung spiegelt nicht mit der festgelegten Zeitzone für diese Zeit wider.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dass das Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Durchführen arithmetischer Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)
