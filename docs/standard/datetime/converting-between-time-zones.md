---
title: Konvertieren von Uhrzeiten zwischen Zeitzonen
description: Erfahren Sie, wie Sie in .net Zeiten zwischen einer Zeitzone in eine andere konvertieren. Außerdem wird beschrieben, wie Sie DateTimeOffset-Werte konvertieren, die nur begrenzte Zeitzoneninformationen aufweisen.
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET], converting
- time zones [.NET], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
ms.openlocfilehash: 3539b3c2b71be331bdea3161b7e8ba6da407cbab
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063832"
---
# <a name="converting-times-between-time-zones"></a>Konvertieren von Uhrzeiten zwischen Zeitzonen

Es wird immer wichtiger, dass Anwendungen, die mit Daten und Uhrzeiten arbeiten, Unterschiede zwischen Zeitzonen verarbeiten können. Eine Anwendung kann nicht mehr davon ausgehen, dass alle Uhrzeiten in der Ortszeit ausgedrückt werden können. Dies ist die Zeit, die in der Struktur verfügbar ist <xref:System.DateTime> . Eine Webseite beispielsweise, die die aktuelle Uhrzeit für die Ostküste der USA anzeigt, wird für Kunden in Ostasien an Glaubwürdigkeit verlieren. In diesem Thema wird erläutert, wie Sie Uhrzeiten von einer Zeitzone in eine andere konvertieren können, und wie Sie <xref:System.DateTimeOffset> Werte mit eingeschränkter Zeit Zonen Bekanntheit konvertieren.

## <a name="converting-to-coordinated-universal-time"></a>Konvertieren in die koordinierte Weltzeit

Die koordinierte Weltzeit (UTC, Coordinated Universal Time) ist ein auf der Atomzeit basierender, höchst präziser Zeitstandard. Die Zeitzonen der Welt werden als positive oder negative Offsets von UTC ausgedrückt. Daher ist die UTC sozusagen eine zeitzonenfreie bzw. zeitzonenneutrale Zeit. Die Verwendung der UTC wird empfohlen, wenn die computerübergreifende Portabilität von Datum und Uhrzeit von großer Bedeutung ist. (Ausführliche Informationen und weitere bewährte Methoden zum Verwenden von Datums-und [Uhrzeitangaben finden Sie unter Programmieren bewährter Methoden mithilfe von DateTime in der .NET Framework](/previous-versions/dotnet/articles/ms973825(v=msdn.10)).) Durch das umrechnen einzelner Zeitzonen in die UTC werden Zeit Vergleiche leicht.

> [!NOTE]
> Sie können auch eine Struktur serialisieren <xref:System.DateTimeOffset> , um einen bestimmten Zeitpunkt eindeutig darzustellen. Da- <xref:System.DateTimeOffset> Objekte einen Datums-und Uhrzeitwert zusammen mit dem Offset von der UTC speichern, stellen Sie immer einen bestimmten Zeitpunkt in Beziehung zu UTC dar.

Die einfachste Möglichkeit, eine Uhrzeit in die UTC zu konvertieren, besteht darin, die- `static` `Shared` Methode (in Visual Basic) aufzurufen <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> . Die genaue Konvertierung, die von der-Methode durchgeführt wird, hängt vom Wert der `dateTime` -Eigenschaft des-Parameters ab <xref:System.DateTime.Kind%2A> , wie in der folgenden Tabelle gezeigt.

| `DateTime.Kind`            | Konvertierung                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Konvertiert die lokale Zeit in die UTC.                                                    |
| `DateTimeKind.Unspecified` | Nimmt an, dass der `dateTime`-Parameter die lokale Zeit angibt, und konvertiert die lokale Zeit in die UTC. |
| `DateTimeKind.Utc`         | Gibt den `dateTime`-Parameter unverändert zurück.                                    |

Der folgende Code konvertiert die aktuelle lokale Zeit in die UTC und zeigt das Ergebnis in der Konsole an.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Wenn der Datums-und Uhrzeitwert weder die Ortszeit noch UTC darstellt, gibt die <xref:System.DateTime.ToUniversalTime%2A> Methode wahrscheinlich ein falsches Ergebnis zurück. Sie können jedoch die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> -Methode verwenden, um das Datum und die Uhrzeit aus einer angegebenen Zeitzone zu konvertieren. (Ausführliche Informationen zum Abrufen eines- <xref:System.TimeZoneInfo> Objekts, das die Ziel Zeitzone darstellt, finden Sie untersuchen [der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md).) Im folgenden Code wird die- <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> Methode verwendet, um die Eastern Standard Time in die UTC zu konvertieren.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Beachten Sie, dass diese Methode einen auslöst, <xref:System.ArgumentException> Wenn die <xref:System.DateTime> -Eigenschaft des-Objekts <xref:System.DateTime.Kind%2A> und die Zeitzone nicht übereinstimmen. Ein Konflikt tritt auf, wenn die- <xref:System.DateTime.Kind%2A> Eigenschaft ist <xref:System.DateTimeKind.Local?displayProperty=nameWithType> , das- <xref:System.TimeZoneInfo> Objekt jedoch nicht die lokale Zeitzone darstellt, oder wenn die- <xref:System.DateTime.Kind%2A> Eigenschaft ist, <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> aber das- <xref:System.TimeZoneInfo> Objekt nicht gleich ist <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType> .

Alle diese Methoden übernehmen <xref:System.DateTime> Werte als Parameter und geben einen <xref:System.DateTime> Wert zurück. Für- <xref:System.DateTimeOffset> Werte verfügt die- <xref:System.DateTimeOffset> Struktur über eine- <xref:System.DateTimeOffset.ToUniversalTime%2A> Instanzmethode, die das Datum und die Uhrzeit der aktuellen Instanz in die UTC konvertiert. Im folgenden Beispiel wird die <xref:System.DateTimeOffset.ToUniversalTime%2A> -Methode aufgerufen, um eine lokale Uhrzeit und einige andere Uhrzeiten in die koordinierte Weltzeit (UTC) zu konvertieren.

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Konvertieren der UTC in eine festgelegte Zeitzone

Informationen zum Konvertieren der UTC in eine lokale Zeit finden Sie im folgenden Abschnitt "Konvertieren der UTC in eine lokale Zeit". Um die UTC in die Zeit in einer von Ihnen festgelegten Zeitzone zu konvertieren, müssen Sie die-Methode aufzurufen <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> . Die Methode akzeptiert zwei Parameter:

- Die zu konvertierende UTC. Dabei muss es sich <xref:System.DateTime> um einen Wert handeln, dessen- <xref:System.DateTime.Kind%2A> Eigenschaft auf oder festgelegt ist `Unspecified` `Utc` .

- Die Zeitzone, in die die UTC konvertiert werden soll.

Der folgende Code konvertiert die UTC in die Central Standard Time.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Konvertieren der UTC in eine lokale Zeit

Um die UTC in die lokale Zeit zu konvertieren, müssen Sie die-Methode des-Objekts aufzurufen, <xref:System.DateTime.ToLocalTime%2A> <xref:System.DateTime> dessen Zeit Sie konvertieren möchten. Das genaue Verhalten der-Methode hängt vom Wert der-Eigenschaft des-Objekts ab <xref:System.DateTime.Kind%2A> , wie in der folgenden Tabelle gezeigt.

| `DateTime.Kind`            | Konvertierung                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Gibt den <xref:System.DateTime> Wert unverändert zurück.                                      |
| `DateTimeKind.Unspecified` | Geht davon aus, dass der <xref:System.DateTime> Wert UTC ist, und konvertiert die UTC in die lokale Zeit. |
| `DateTimeKind.Utc`         | Konvertiert den <xref:System.DateTime> Wert in die lokale Zeit.                                 |

> [!NOTE]
> Die- <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> Methode verhält sich identisch mit der- `DateTime.ToLocalTime` Methode. Er nimmt einen einzelnen Parameter an, der den zu konvertierenden Datums-und Uhrzeitwert ist.

Mithilfe der `static` ( `Shared` in Visual Basic)-Methode können Sie auch die Zeit in einer bestimmten Zeitzone in lokale Zeit konvertieren <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> . Diese Vorgehensweise wird im nächsten Abschnitt erläutert.

## <a name="converting-between-any-two-time-zones"></a>Konvertieren zwischen zwei beliebigen Zeitzonen

Sie können zwischen zwei beliebigen Zeitzonen konvertieren, indem Sie eine der beiden folgenden `static` Methoden ( `Shared` in Visual Basic) der- <xref:System.TimeZoneInfo> Klasse verwenden:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  Die Parameter dieser Methode sind der zu konvertierende Datums-und Uhrzeitwert, ein `TimeZoneInfo` -Objekt, das die Zeitzone des Datums-und Uhrzeitwerts darstellt, und ein- `TimeZoneInfo` Objekt, das die Zeitzone darstellt, in die der Datums-und Uhrzeitwert konvertiert werden soll.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Die Parameter dieser Methode sind der zu konvertierende Datums-und Uhrzeitwert, der Bezeichner für die Zeitzone des Datums-und Uhrzeitwerts und der Bezeichner der Zeitzone, in die der Datums-und Uhrzeitwert konvertiert werden soll.

Beide Methoden erfordern, dass die <xref:System.DateTime.Kind%2A> -Eigenschaft des zu konvertierenden Datums-und Uhrzeitwerts und der <xref:System.TimeZoneInfo> Objekt-oder Zeit Zonen Bezeichner, der die Zeitzone darstellt, einander entsprechen. Andernfalls wird eine <xref:System.ArgumentException> ausgelöst. Wenn beispielsweise die `Kind` -Eigenschaft des Datums-und Uhrzeitwerts ist `DateTimeKind.Local` , wird eine-Ausnahme ausgelöst, wenn das Objekt, das `TimeZoneInfo` als Parameter an die-Methode übergeben wurde, nicht gleich ist `TimeZoneInfo.Local` . Eine Ausnahme wird auch ausgelöst, wenn der als Parameter an die Methode übergebene Bezeichner nicht gleich ist `TimeZoneInfo.Local.Id` .

Im folgenden Beispiel wird die- <xref:System.TimeZoneInfo.ConvertTime%2A> Methode verwendet, um von der Hawaii-Standard Zeit in die lokale Uhrzeit zu konvertieren.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Konvertieren von DateTimeOffset-Werten

Datums-und Uhrzeitwerte, die durch- <xref:System.DateTimeOffset> Objekte dargestellt werden, sind nicht vollständig Zeit Zonen fähig, da das-Objekt zu dem Zeitpunkt, zu dem er instanziiert wird, von der Zeitzone getrennt wird. In vielen Fällen muss eine Anwendung jedoch einfach nur ein Datum und eine Uhrzeit basierend auf zwei verschiedenen Abweichungen von der UTC konvertieren, nicht basierend auf der Uhrzeit in bestimmten Zeitzonen. Um diese Konvertierung auszuführen, können Sie die-Methode der aktuellen Instanz von aufzurufen <xref:System.DateTimeOffset.ToOffset%2A> . Der einzige Parameter der Methode ist der Offset des neuen Datums-und Uhrzeitwerts, der von der Methode zurückgegeben werden soll.

Wenn Datum und Uhrzeit einer Benutzeranforderung für eine Webseite bekannt sind und als Zeichenfolge im Format MM/dd/yyyy hh:mm:ss zzzz serialisiert wurden, konvertiert die folgende `ReturnTimeOnServer`-Methode diesen Datums- und Uhrzeitwert in das Datum und die Uhrzeit des Webservers.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]

Wenn der-Methode die Zeichenfolge "9/1/2007 5:32:07 -05:00", die das Datum und die Uhrzeit in einer Zeitzone von fünf Stunden vor der UTC darstellt, an die-Methode zurückgegeben wird, gibt Sie 9/1/2007 3:32:07 am-07:00 für einen Server zurück, der sich in der US Pacific Standard Time Zone befindet.

Die- <xref:System.TimeZoneInfo> Klasse enthält auch eine Überladung der- <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> Methode, die Zeit Zonen Konvertierungen mit- <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> Werten ausführt. Die Parameter der Methode sind ein <xref:System.DateTimeOffset> Wert und ein Verweis auf die Zeitzone, in die die Uhrzeit konvertiert werden soll. Der Methoden Aufrufwert gibt einen- <xref:System.DateTimeOffset> Wert zurück. Die- `ReturnTimeOnServer` Methode im vorherigen Beispiel könnte z. b. wie folgt umgeschrieben werden, um die-Methode aufzurufen <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> .

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Siehe auch

- <xref:System.TimeZoneInfo>
- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md)
