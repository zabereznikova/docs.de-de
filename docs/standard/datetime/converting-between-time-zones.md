---
title: Konvertieren von Uhrzeiten zwischen Zeitzonen
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
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 58ed01520a9bbed53d32fc10e48a479e68f6ef7c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="converting-times-between-time-zones"></a>Konvertieren von Uhrzeiten zwischen Zeitzonen

Es wird immer wichtiger, dass Anwendungen, die mit Daten und Uhrzeiten arbeiten, Unterschiede zwischen Zeitzonen verarbeiten können. Eine Anwendung kann nicht mehr davon ausgehen, die jederzeit ausgedrückt werden können in die Ortszeit steht die Zeit aus der <xref:System.DateTime> Struktur. Eine Webseite beispielsweise, die die aktuelle Uhrzeit für die Ostküste der USA anzeigt, wird für Kunden in Ostasien an Glaubwürdigkeit verlieren. In diesem Thema wird erläutert, wie oft aus einer Zeitzone in eine andere zu konvertieren sowie zum Konvertieren <xref:System.DateTimeOffset> Werte, die Zeitzonen begrenzt ist.

## <a name="converting-to-coordinated-universal-time"></a>Konvertieren in die koordinierte Weltzeit

Die koordinierte Weltzeit (UTC, Coordinated Universal Time) ist ein auf der Atomzeit basierender, höchst präziser Zeitstandard. Die Zeitzonen der Welt werden als positive oder negative Abweichungen von der UTC ausgedrückt. Daher ist die UTC sozusagen eine zeitzonenfreie bzw. zeitzonenneutrale Zeit. Die Verwendung der UTC wird empfohlen, wenn die computerübergreifende Portabilität von Datum und Uhrzeit von großer Bedeutung ist. (Details und weitere bewährten Methoden, die mit Datumsangaben und Uhrzeiten, finden Sie unter [Codierung bewährte Methoden, die mit "DateTime" in .NET Framework](http://go.microsoft.com/fwlink/?LinkId=92342).) Durch Konvertieren einzelner Zeitzonen in die UTC lassen sich Zeiten einfach miteinander vergleichen.

> [!NOTE]
> Sie können auch Serialisieren einer <xref:System.DateTimeOffset> Struktur, um einen einzigen Zeitpunkt eindeutig einen bestimmten Zeitraum darstellen. Da <xref:System.DateTimeOffset> einen Datum und Uhrzeit-Wert zusammen mit dem Offset von UTC zum Speichern von Objekten, die sie immer einen bestimmten Zeitpunkt darstellen in Beziehung in UTC.

Die einfachste Möglichkeit zum Konvertieren einer Uhrzeit in UTC-Zeit ist das Aufrufen der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> Methode. Die tatsächlich von der Methode ausgeführte Konvertierung hängt vom Wert von der `dateTime` des Parameters <xref:System.DateTime.Kind%2A> Eigenschaft, wie in der folgenden Tabelle gezeigt.

| `DateTime.Kind`            | Umwandeln                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Konvertiert die lokale Zeit in die UTC.                                                    |
| `DateTimeKind.Unspecified` | Nimmt an, dass der `dateTime`-Parameter die lokale Zeit angibt, und konvertiert die lokale Zeit in die UTC. |
| `DateTimeKind.Utc`         | Gibt den `dateTime`-Parameter unverändert zurück.                                    |

Der folgende Code konvertiert die aktuelle lokale Zeit in die UTC und zeigt das Ergebnis in der Konsole an.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> Die <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> Methode gibt die Ergebnisse, die identisch sind nicht notwendigerweise zurück die <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> und <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> Methoden. Wenn das Hostsystem den lokalen enthält Zeitzone mehrere Anpassungsregeln <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> gilt die entsprechende Regel auf ein bestimmtes Datum und Uhrzeit. Die anderen beiden Methoden wenden immer die jüngste Anpassungsregel an.

Wenn der Wert für Datum und Uhrzeit nicht der Ortszeit oder UTC darstellen der <xref:System.DateTime.ToUniversalTime%2A> Methode wird wahrscheinlich ein falsches Ergebnis zurück. Sie können jedoch die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> Methode zum Konvertieren von Datums- und Uhrzeitangabe von einer angegebenen Zeitzone. (Weitere Informationen über das Abrufen von einem <xref:System.TimeZoneInfo> Objekt, das die Zielzeitzone darstellt finden Sie unter [suchen die in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) Der folgende code verwendet die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> Methode, um Eastern Standard Time, UTC konvertieren.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Beachten Sie, die diese Methode löst eine <xref:System.ArgumentException> Wenn die <xref:System.DateTime> des Objekts <xref:System.DateTime.Kind%2A> Eigenschaft und die Zeitzone stimmen nicht überein. Ein Konflikt tritt auf, wenn die <xref:System.DateTime.Kind%2A> Eigenschaft ist <xref:System.DateTimeKind?displayProperty=nameWithType> aber die <xref:System.TimeZoneInfo> Objekt ist nicht die lokale Zeitzone darstellen oder wenn die <xref:System.DateTime.Kind%2A> Eigenschaft ist <xref:System.DateTimeKind?displayProperty=nameWithType> aber die <xref:System.TimeZoneInfo> Objekt ist nicht gleich <xref:System.DateTimeKind?displayProperty=nameWithType>.

Alle diese Methoden nehmen <xref:System.DateTime> Werte als Parameter und Rückgabetypen einer <xref:System.DateTime> Wert. Für <xref:System.DateTimeOffset> Werte, die <xref:System.DateTimeOffset> Struktur verfügt über eine <xref:System.DateTimeOffset.ToUniversalTime%2A> -Instanzmethode, der das Datum und die Uhrzeit der aktuellen Instanz in UTC konvertiert. Im folgenden Beispiel wird die <xref:System.DateTimeOffset.ToUniversalTime%2A> Methode, um eine Ortszeit und mehrere andere Uhrzeiten in Coordinated Universal Time (UTC) konvertieren.

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Konvertieren der UTC in eine festgelegte Zeitzone

Konvertieren von UTC in die Ortszeit finden Sie im Abschnitt "Konvertieren von UTC in Ortszeit", der folgt. Aufrufen, um die Zeit in eine beliebige Zeitzone UTC konvertieren, die Sie festlegen, die <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> Methode. Die Methode akzeptiert zwei Parameter:

* Die zu konvertierende UTC. Diese Angabe muss ein <xref:System.DateTime> , dessen Wert <xref:System.DateTime.Kind%2A> -Eigenschaftensatz auf <xref:System.DateTimeKind?displayProperty=nameWithType> oder <xref:System.DateTimeKind?displayProperty=nameWithType>.

* Die Zeitzone, in die die UTC konvertiert werden soll.

Der folgende Code konvertiert die UTC in die Central Standard Time.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Konvertieren der UTC in eine lokale Zeit

Rufen Sie zum Konvertieren von UTC in die Ortszeit der <xref:System.DateTime.ToLocalTime%2A> Methode der <xref:System.DateTime> Objekt, dessen Zeit, die Sie konvertieren möchten. Das genaue Verhalten der Methode hängt vom Wert des Objekts <xref:System.DateTime.Kind%2A> Eigenschaft, wie in der folgenden Tabelle gezeigt.

| `DateTime.Kind`            | Umwandeln                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Gibt die <xref:System.DateTime> Wert unverändert.                                      |
| `DateTimeKind.Unspecified` | Setzt voraus, dass die <xref:System.DateTime> Wert UTC ist, und die UTC-Zeit in die Ortszeit konvertiert. |
| `DateTimeKind.Utc`         | Konvertiert die <xref:System.DateTime> Wert in die Ortszeit.                                 |

> [!NOTE]
> Die <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> Methode verhält sich genauso wie die `DateTime.ToLocalTime` Methode. Er nimmt einen Parameter, dies ist der Wert für Datum und Uhrzeit zu konvertieren.

Sie können auch die Zeit in einer beliebigen Zeitzone in lokale Zeit konvertieren, mithilfe der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> Methode. Diese Technik wird im nächsten Abschnitt erläutert.

## <a name="converting-between-any-two-time-zones"></a>Konvertieren zwischen zwei beliebigen Zeitzonen

Sie können zwischen zwei beliebigen Zeitzonen mithilfe einer der folgenden beiden konvertieren `static` (`Shared` in Visual Basic) Methoden der <xref:System.TimeZoneInfo> Klasse:

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  Die Parameter dieser Methode sind Wert für Datum und Uhrzeit zu konvertieren, eine `TimeZoneInfo` -Objekt, das der Wert für Datum und Uhrzeit, das die Zeitzone darstellt und ein `TimeZoneInfo` -Objekt, das zu konvertierende Wert für Datum und Uhrzeit, das die Zeitzone darstellt.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Die Parameter dieser Methode werden das Datum und, die zu konvertierende Zeitwert, der Bezeichner des Datums- und Uhrzeitwerts Zeitzone und der Bezeichner der Zeitzone Wert für Datum und Uhrzeit zu konvertieren.

Beide Methoden erfordern, die die <xref:System.DateTime.Kind%2A> Eigenschaft von der zu konvertierende Datums- und Uhrzeitangabe Wert und die <xref:System.TimeZoneInfo> Objekt oder der Zeitzonenbezeichner, der die Zeitzone darstellt, einander entsprechen. Andernfalls ein <xref:System.ArgumentException> ausgelöst wird. Z. B. wenn die `Kind` Eigenschaft der Wert für Datum und Uhrzeit ist `DateTimeKind.Local`, eine Ausnahme wird ausgelöst, wenn die `TimeZoneInfo` als Parameter an die Methode übergebenen Objekts ist nicht gleich `TimeZoneInfo.Local`. Eine Ausnahme wird auch ausgelöst, wenn der als Parameter an die Methode übergebene Bezeichner nicht gleich `TimeZoneInfo.Local.Id`.

Im folgenden Beispiel wird die <xref:System.TimeZoneInfo.ConvertTime%2A> -Methode zum Konvertieren von Hawaii Normalzeit in die Ortszeit.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Konvertieren von DateTimeOffset-Werten

Datum und Uhrzeit-Werte, die dargestellte <xref:System.DateTimeOffset> Objekte sind nicht vollständig Zeitzone bekannt, da das Objekt zum Zeitpunkt seiner Zeitzone aufgehoben ist er instanziiert wird. In vielen Fällen muss eine Anwendung jedoch einfach nur ein Datum und eine Uhrzeit basierend auf zwei verschiedenen Abweichungen von der UTC konvertieren, nicht basierend auf der Uhrzeit in bestimmten Zeitzonen. Um diese Konvertierung auszuführen, können Sie der aktuellen Instanz aufrufen <xref:System.DateTimeOffset.ToOffset%2A> Methode. Einzige Parameter der Methode ist der Offset des neuen Datums- und Uhrzeitwert, der die Methode zurück.

Wenn Datum und Uhrzeit einer Benutzeranforderung für eine Webseite bekannt sind und als Zeichenfolge im Format MM/dd/yyyy hh:mm:ss zzzz serialisiert wurden, konvertiert die folgende `ReturnTimeOnServer`-Methode diesen Datums- und Uhrzeitwert in das Datum und die Uhrzeit des Webservers.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Beispiel: An diese Methode wird die Zeichenfolge „9/1/2007 5:32:07 -05:00“ übergeben. Diese stellt das Datum und die Uhrzeit in einer Zeitzone dar, die fünf Stunden vor der UTC liegt. In diesem Fall gibt die Methode den Wert „9/1/2007 3:32:07 AM -07:00“ zurück, wenn sich der Server in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.

Die <xref:System.TimeZoneInfo> Klasse enthält auch eine Überladung der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> -Methode, die von der zeitzonenkonvertierungen mit <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> Werte. Parameter der Methode sind ein <xref:System.DateTimeOffset> Wert und einem Verweis auf die Zeitzone, zu deren Verwendung die Zeit ist, konvertiert werden soll. Aufruf der Methode gibt ein <xref:System.DateTimeOffset> Wert. Z. B. die `ReturnTimeOnServer` Methode im vorherigen Beispiel könnte folgendermaßen umgeschrieben werden, zum Aufrufen der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> Methode.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Siehe auch

<xref:System.TimeZoneInfo>[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[suchen die in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
