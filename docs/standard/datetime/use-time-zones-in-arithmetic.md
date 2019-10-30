---
title: 'Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums-und Uhrzeit Operationen'
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
ms.openlocfilehash: 1acd53fad6b0ab173f855850353339190ebdd893
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132540"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums-und Uhrzeit Operationen

Wenn Sie Datums-und Uhrzeit Arithmetik mit <xref:System.DateTime>-oder <xref:System.DateTimeOffset>-Werten ausführen, spiegelt das Ergebnis normalerweise keine Zeit Zonen Anpassungsregeln wider. Dies gilt auch, wenn die Zeitzone des Datums-und Uhrzeitwerts eindeutig erkennbar ist (z. b. wenn die <xref:System.DateTime.Kind%2A>-Eigenschaft auf <xref:System.DateTimeKind.Local>festgelegt ist). In diesem Thema wird gezeigt, wie arithmetische Operationen für Datums-und Uhrzeitwerte durchgeführt werden, die zu einer bestimmten Zeitzone gehören. Die Ergebnisse der arithmetischen Operationen berücksichtigen die Anpassungsregeln der Zeitzone.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>So wenden Sie Anpassungsregeln auf arithmetische Datums- und Uhrzeitoperationen an

1. Implementieren Sie eine beliebige Methode, mit der ein Datums- und Uhrzeitwert eng mit der Zeitzone verknüpft wird, zu der er gehört. Deklarieren Sie z.B. eine Struktur, die sowohl den Datums- als auch den Uhrzeitwert und die Zeitzone einschließt. Im folgenden Beispiel wird dieser Ansatz verwendet, um einen <xref:System.DateTime>-Wert mit seiner Zeitzone zu verknüpfen.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Konvertieren Sie eine Uhrzeit in eine koordinierte Weltzeit (UTC), indem Sie entweder die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>-Methode oder die <xref:System.TimeZoneInfo.ConvertTime%2A>-Methode aufrufen.

3. Führen Sie die arithmetische Operation für die UTC-Zeit aus.

4. Konvertieren Sie die Zeit von UTC in die zugehörige Zeitzone der ursprünglichen Zeit, indem Sie die <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>-Methode aufrufen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Stunden und 30 Minuten zum 9. März 2008 um 1:30 Uhr Central Standard Time hinzugefügt. Die Umstellung auf Sommerzeit erfolgt in der Zeitzone dreißig Minuten später, um 2:00 Uhr am 9. März 2008 hinzugefügt wurden. Da das Beispiel den vier Schritten folgt, die im vorherigen Abschnitt aufgeführt sind, ist das Ergebnis die richtige Zeit von 5:00 Uhr am 9. März 2008 hinzugefügt wurden.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Sowohl <xref:System.DateTime> als auch <xref:System.DateTimeOffset> Werte werden von jeder Zeitzone, zu der Sie gehören, getrennt. Um arithmetische Datums- und Uhrzeitoperationen so durchführen zu können, dass Anpassungsregeln für Zeitzonen automatisch angewendet werden, muss die Zeitzone, zu der der Datums- und Uhrzeitwert gehört, direkt identifizierbar sein. Dies bedeutet, dass Datum und Uhrzeit sowie die zugeordnete Zeitzone eng verknüpft sein müssen. Hierzu gibt es mehrere Möglichkeiten, darunter die folgenden:

- Nehmen Sie an, dass alle in einer Anwendung verwendeten Uhrzeiten zu einer bestimmten Zeitzone gehören. Obwohl dieser Ansatz in einigen Fällen geeignet ist, bietet er jedoch nur eingeschränkte Flexibilität sowie möglicherweise eine eingeschränkte Portabilität.

- Definieren Sie einen Typ, der ein Datum und eine Uhrzeit eng mit der zugehörigen Zeitzone verknüpft, indem Sie beide als Felder des Typs einschließen. Dieser Ansatz wird im Codebeispiel verwendet, in dem eine Struktur zum Speichern des Datums und der Uhrzeit sowie der Zeitzone in zwei Memberfeldern definiert wird.

Das Beispiel veranschaulicht, wie arithmetische Operationen für <xref:System.DateTime> Werte ausgeführt werden, sodass Zeit Zonen Anpassungsregeln auf das Ergebnis angewendet werden. Allerdings können <xref:System.DateTimeOffset> Werte genauso einfach verwendet werden. Im folgenden Beispiel wird veranschaulicht, wie der Code im ursprünglichen Beispiel so angepasst werden kann, dass anstelle <xref:System.DateTime> Werte <xref:System.DateTimeOffset> verwendet werden.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Beachten Sie Folgendes: Wenn diese Addition einfach für den <xref:System.DateTimeOffset> Wert ausgeführt wird, ohne Sie zuerst in die UTC zu umrechnen, gibt das Ergebnis den richtigen Zeitpunkt wieder, aber die Abweichung spiegelt nicht die der festgelegten Zeitzone für diese Uhrzeit wider.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- , Dass der <xref:System> Namespace mit der `using`-Anweisung importiert werden soll C# (erforderlich im Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Durchführen arithmetischer Datums- und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)
