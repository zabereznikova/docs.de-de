---
title: 'Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16f90117353c490b0a6f7b7fe94730d90e797b35
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>Vorgehensweise: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen

Normalerweise beim Ausführen von Datum und Zeit arithmetische <xref:System.DateTime> oder <xref:System.DateTimeOffset> Werte, die das Ergebnis sind keine Regeln zur Anpassung der Zeitzone enthalten. Dies ist "true", selbst wenn der Wert für Datum und Uhrzeit der Zeitzone eindeutig erkennbar ist (z. B. wenn die <xref:System.DateTime.Kind%2A> -Eigenschaftensatz auf <xref:System.DateTimeKind.Local>). In diesem Thema wird gezeigt, wie arithmetische Operationen für Datums-und Uhrzeitwerte ausgeführt, die zu einer bestimmten Zeitzone gehören. Die Ergebnisse der arithmetischen Operationen berücksichtigen die Anpassungsregeln der Zeitzone.

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>So wenden Sie Anpassungsregeln auf arithmetische Datums- und Uhrzeitoperationen an

1. Implementieren Sie eine beliebige Methode, mit der ein Datums- und Uhrzeitwert eng mit der Zeitzone verknüpft wird, zu der er gehört. Deklarieren Sie z.B. eine Struktur, die sowohl den Datums- als auch den Uhrzeitwert und die Zeitzone einschließt. Im folgenden Beispiel wird dieser Ansatz zum Verknüpfen einer <xref:System.DateTime> Wert mit seiner Zeitzone.

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. Konvertiert eine Uhrzeit in Coordinated Universal Time (UTC) durch Aufrufen der <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> Methode oder die <xref:System.TimeZoneInfo.ConvertTime%2A> Methode.

3. Führen Sie die arithmetische Operation für die UTC-Zeit aus.

4. Die Zeit von UTC in die ursprüngliche Uhrzeit zugehörigen Zeitzone zu konvertieren, durch Aufrufen der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> Methode.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Stunden und 30 Minuten zum 9. März 2008 um 1:30 Uhr Central Standard Time hinzugefügt. Die Umstellung auf Sommerzeit erfolgt in der Zeitzone dreißig Minuten später, um 2:00 Uhr am 9.März 2008. Da das Beispiel den vier Schritten folgt, die im vorherigen Abschnitt aufgeführt sind, ist das Ergebnis die richtige Zeit von 5:00 Uhr am 9. März 2008.

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

Beide <xref:System.DateTime> und <xref:System.DateTimeOffset> Werte werden an eine beliebige Zeitzone, zu dem sie gehören möglicherweise, aufgehoben. Um arithmetische Datums- und Uhrzeitoperationen so durchführen zu können, dass Anpassungsregeln für Zeitzonen automatisch angewendet werden, muss die Zeitzone, zu der der Datums- und Uhrzeitwert gehört, direkt identifizierbar sein. Dies bedeutet, dass Datum und Uhrzeit sowie die zugeordnete Zeitzone eng verknüpft sein müssen. Hierzu gibt es mehrere Möglichkeiten, darunter die folgenden:

* Nehmen Sie an, dass alle in einer Anwendung verwendeten Uhrzeiten zu einer bestimmten Zeitzone gehören. Obwohl dieser Ansatz in einigen Fällen geeignet ist, bietet er jedoch nur eingeschränkte Flexibilität sowie möglicherweise eine eingeschränkte Portabilität.

* Definieren Sie einen Typ, der ein Datum und eine Uhrzeit eng mit der zugehörigen Zeitzone verknüpft, indem Sie beide als Felder des Typs einschließen. Dieser Ansatz wird im Codebeispiel verwendet, in dem eine Struktur zum Speichern des Datums und der Uhrzeit sowie der Zeitzone in zwei Memberfeldern definiert wird.

Im Beispiel wird veranschaulicht, wie arithmetische Operationen für <xref:System.DateTime> Werte so, dass die Regeln zur Anpassung der Zeitzone auf das Ergebnis angewendet werden. Allerdings <xref:System.DateTimeOffset> Werte genauso einfach verwendet werden können. Im folgende Beispiel wird veranschaulicht, wie der Code im ursprünglichen Beispiel angepasst werden möglicherweise <xref:System.DateTimeOffset> anstelle von <xref:System.DateTime> Werte.

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

Beachten Sie, dass diese Ergänzung einfach nach erfolgt die <xref:System.DateTimeOffset> ohne zuerst in UTC konvertiert, das Ergebnis richtigen Zeitpunkt zeitlich wobei der Offset ist nicht widerspiegelt, die der festgelegten Zeitzone für diese Zeit-Wert.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[durchführen arithmetischer Datums-und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)
