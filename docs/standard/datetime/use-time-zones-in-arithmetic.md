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
ms.openlocfilehash: af19145f7caa9dbe8630ae7593734769e98720d0
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280919"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen

Wenn Sie Datums-und Uhrzeit Berechnungen mithilfe von- <xref:System.DateTime> oder-Werten durchführen <xref:System.DateTimeOffset> , spiegelt das Ergebnis normalerweise keine Zeit Zonen Anpassungsregeln wider. Dies trifft auch dann zu, wenn die Zeitzone des Datums-und Uhrzeitwerts eindeutig erkennbar ist (z. b. wenn die- <xref:System.DateTime.Kind%2A> Eigenschaft auf festgelegt ist <xref:System.DateTimeKind.Local> ). In diesem Thema wird gezeigt, wie arithmetische Operationen für Datums-und Uhrzeitwerte durchgeführt werden, die zu einer bestimmten Zeitzone gehören. Die Ergebnisse der arithmetischen Operationen berücksichtigen die Anpassungsregeln der Zeitzone.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>So wenden Sie Anpassungsregeln auf arithmetische Datums- und Uhrzeitoperationen an

1. Implementieren Sie eine beliebige Methode, mit der ein Datums- und Uhrzeitwert eng mit der Zeitzone verknüpft wird, zu der er gehört. Deklarieren Sie z.B. eine Struktur, die sowohl den Datums- als auch den Uhrzeitwert und die Zeitzone einschließt. Im folgenden Beispiel wird dieser Ansatz verwendet, um einen- <xref:System.DateTime> Wert mit seiner Zeitzone zu verknüpfen.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Konvertieren Sie eine Uhrzeit in eine koordinierte Weltzeit (UTC), indem Sie entweder die- <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> Methode oder die- <xref:System.TimeZoneInfo.ConvertTime%2A> Methode aufrufen.

3. Führen Sie die arithmetische Operation für die UTC-Zeit aus.

4. Konvertieren Sie die Zeit von UTC in die zugehörige Zeitzone der ursprünglichen Zeit, indem Sie die- <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> Methode aufrufen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Stunden und 30 Minuten zum 9. März 2008 um 1:30 Uhr Central Standard Time hinzugefügt. Die Umstellung auf Sommerzeit erfolgt in der Zeitzone dreißig Minuten später, um 2:00 Uhr am 9. März 2008 hinzugefügt wurden. Da das Beispiel den vier Schritten folgt, die im vorherigen Abschnitt aufgeführt sind, ist das Ergebnis die richtige Zeit von 5:00 Uhr am 9. März 2008 hinzugefügt wurden.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Der <xref:System.DateTime> - <xref:System.DateTimeOffset> Wert und der-Wert werden von jeder Zeitzone, zu der Sie gehören, getrennt. Um arithmetische Datums- und Uhrzeitoperationen so durchführen zu können, dass Anpassungsregeln für Zeitzonen automatisch angewendet werden, muss die Zeitzone, zu der der Datums- und Uhrzeitwert gehört, direkt identifizierbar sein. Dies bedeutet, dass Datum und Uhrzeit sowie die zugeordnete Zeitzone eng verknüpft sein müssen. Hierzu gibt es mehrere Möglichkeiten, darunter die folgenden:

- Nehmen Sie an, dass alle in einer Anwendung verwendeten Uhrzeiten zu einer bestimmten Zeitzone gehören. Obwohl dieser Ansatz in einigen Fällen geeignet ist, bietet er jedoch nur eingeschränkte Flexibilität sowie möglicherweise eine eingeschränkte Portabilität.

- Definieren Sie einen Typ, der ein Datum und eine Uhrzeit eng mit der zugehörigen Zeitzone verknüpft, indem Sie beide als Felder des Typs einschließen. Dieser Ansatz wird im Codebeispiel verwendet, in dem eine Struktur zum Speichern des Datums und der Uhrzeit sowie der Zeitzone in zwei Memberfeldern definiert wird.

Das Beispiel veranschaulicht, wie arithmetische Operationen für- <xref:System.DateTime> Werte ausgeführt werden, sodass Zeit Zonen Anpassungsregeln auf das Ergebnis angewendet werden. <xref:System.DateTimeOffset>Werte können jedoch genauso einfach verwendet werden. Im folgenden Beispiel wird veranschaulicht, wie der Code im ursprünglichen Beispiel so angepasst werden kann, dass <xref:System.DateTimeOffset> anstelle von-Werten verwendet wird <xref:System.DateTime> .

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Beachten Sie Folgendes: Wenn diese Addition einfach für den <xref:System.DateTimeOffset> Wert ausgeführt wird, ohne dass Sie zuerst in UTC-Werte umgerechnet wird, gibt das Ergebnis den richtigen Zeitpunkt wieder, aber die Abweichung spiegelt nicht die der festgelegten Zeitzone für diese Uhrzeit wider.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Der <xref:System> Namespace wird mit der- `using` Anweisung importiert (erforderlich in c#-Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Durchführen arithmetischer Datums- und Uhrzeitoperationen](performing-arithmetic-operations.md)
