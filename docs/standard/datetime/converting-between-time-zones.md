---
title: Konvertieren von Uhrzeiten zwischen Zeitzonen
ms.date: 04/10/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: fbb59dbe364763209f44a4e2241d1d5275036c40
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156022"
---
# <a name="converting-times-between-time-zones"></a>Konvertieren von Uhrzeiten zwischen Zeitzonen

Es wird immer wichtiger, dass Anwendungen, die mit Daten und Uhrzeiten arbeiten, Unterschiede zwischen Zeitzonen verarbeiten können. Eine Anwendung kann nicht mehr davon ausgehen, dass alle Uhrzeiten in der lokalen Zeit ausgedrückt werden können. Dies ist die Zeit, die in der <xref:System.DateTime> Struktur verfügbar ist. Eine Webseite beispielsweise, die die aktuelle Uhrzeit für die Ostküste der USA anzeigt, wird für Kunden in Ostasien an Glaubwürdigkeit verlieren. In diesem Thema wird erläutert, wie Sie Uhrzeiten von einer Zeitzone in eine andere konvertieren und <xref:System.DateTimeOffset> Werte mit eingeschränkter Zeit Zonen Erkennung konvertieren.

## <a name="converting-to-coordinated-universal-time"></a>Konvertieren in die koordinierte Weltzeit

Die koordinierte Weltzeit (UTC, Coordinated Universal Time) ist ein auf der Atomzeit basierender, höchst präziser Zeitstandard. Die Zeitzonen der Welt werden als positive oder negative Abweichungen von der UTC ausgedrückt. Daher ist die UTC sozusagen eine zeitzonenfreie bzw. zeitzonenneutrale Zeit. Die Verwendung der UTC wird empfohlen, wenn die computerübergreifende Portabilität von Datum und Uhrzeit von großer Bedeutung ist. (Ausführliche Informationen und weitere bewährte Methoden zum Verwenden von Datums-und [Uhrzeitangaben finden Sie unter Programmieren bewährter Methoden mithilfe von DateTime in der .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10)).) Durch das umrechnen einzelner Zeitzonen in die UTC werden Zeit Vergleiche leicht.

> [!NOTE]
> Sie können auch eine <xref:System.DateTimeOffset> Struktur serialisieren, um einen bestimmten Zeitpunkt eindeutig darzustellen. Da <xref:System.DateTimeOffset>-Objekte einen Datums-und Uhrzeitwert zusammen mit dem Offset von der UTC speichern, stellen Sie immer einen bestimmten Zeitpunkt in Beziehung zu UTC dar.

Die einfachste Möglichkeit, eine Uhrzeit in die UTC zu konvertieren, besteht darin, die `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>-Methode aufzurufen. Die genaue Konvertierung, die von der-Methode durchgeführt wird, hängt vom Wert der <xref:System.DateTime.Kind%2A>-Eigenschaft des `dateTime`-Parameters ab, wie in der folgenden Tabelle gezeigt.

| `DateTime.Kind`            | Umwandeln                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Konvertiert die lokale Zeit in die UTC.                                                    |
| `DateTimeKind.Unspecified` | Nimmt an, dass der `dateTime`-Parameter die lokale Zeit angibt, und konvertiert die lokale Zeit in die UTC. |
| `DateTimeKind.Utc`         | Gibt den `dateTime`-Parameter unverändert zurück.                                    |

Der folgende Code konvertiert die aktuelle lokale Zeit in die UTC und zeigt das Ergebnis in der Konsole an.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Wenn der Datums-und Uhrzeitwert weder die Ortszeit noch UTC darstellt, gibt die <xref:System.DateTime.ToUniversalTime%2A>-Methode wahrscheinlich ein falsches Ergebnis zurück. Sie können jedoch die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType>-Methode verwenden, um das Datum und die Uhrzeit aus einer angegebenen Zeitzone zu konvertieren. (Ausführliche Informationen zum Abrufen eines <xref:System.TimeZoneInfo> Objekts, das die Ziel Zeitzone darstellt, finden Sie untersuchen [der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) Im folgenden Code wird die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType>-Methode verwendet, um die Eastern Standard Time in die UTC zu konvertieren.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Beachten Sie, dass diese Methode eine <xref:System.ArgumentException> auslöst, wenn die <xref:System.DateTime.Kind%2A>-Eigenschaft des <xref:System.DateTime>-Objekts und die Zeitzone nicht übereinstimmen. Ein Konflikt tritt auf, wenn die <xref:System.DateTime.Kind%2A>-Eigenschaft <xref:System.DateTimeKind.Local?displayProperty=nameWithType> ist, das <xref:System.TimeZoneInfo>-Objekt jedoch nicht die lokale Zeitzone darstellt oder wenn die <xref:System.DateTime.Kind%2A>-Eigenschaft <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> ist, das <xref:System.TimeZoneInfo> Objekt jedoch nicht <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>ist.

Alle diese Methoden übernehmen <xref:System.DateTime> Werte als Parameter und geben einen <xref:System.DateTime> Wert zurück. Bei <xref:System.DateTimeOffset> Werten verfügt die <xref:System.DateTimeOffset> Struktur über eine <xref:System.DateTimeOffset.ToUniversalTime%2A> Instanzmethode, die das Datum und die Uhrzeit der aktuellen Instanz in die UTC konvertiert. Im folgenden Beispiel wird die <xref:System.DateTimeOffset.ToUniversalTime%2A>-Methode aufgerufen, um eine lokale Uhrzeit und einige andere Male in eine koordinierte Weltzeit (UTC) zu konvertieren.

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Konvertieren der UTC in eine festgelegte Zeitzone

Informationen zum Konvertieren der UTC in eine lokale Zeit finden Sie im folgenden Abschnitt "Konvertieren der UTC in eine lokale Zeit". Um die UTC in die Zeit in einer beliebigen von Ihnen festgelegten Zeitzone zu konvertieren, müssen Sie die <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>-Methode aufzurufen. Die Methode akzeptiert zwei Parameter:

- Die zu konvertierende UTC. Dabei muss es sich um einen <xref:System.DateTime> Wert handeln, dessen <xref:System.DateTime.Kind%2A>-Eigenschaft auf `Unspecified` oder `Utc`festgelegt ist.

- Die Zeitzone, in die die UTC konvertiert werden soll.

Der folgende Code konvertiert die UTC in die Central Standard Time.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Konvertieren der UTC in eine lokale Zeit

Um die UTC in die lokale Zeit zu konvertieren, müssen Sie die <xref:System.DateTime.ToLocalTime%2A>-Methode des <xref:System.DateTime>-Objekts, dessen Zeit Sie konvertieren möchten, abrufen. Das genaue Verhalten der-Methode hängt vom Wert der <xref:System.DateTime.Kind%2A>-Eigenschaft des-Objekts ab, wie in der folgenden Tabelle gezeigt.

| `DateTime.Kind`            | Umwandeln                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Gibt den <xref:System.DateTime> Wert unverändert zurück.                                      |
| `DateTimeKind.Unspecified` | Geht davon aus, dass der <xref:System.DateTime> Wert UTC ist, und konvertiert die UTC in die lokale Zeit. |
| `DateTimeKind.Utc`         | Konvertiert den <xref:System.DateTime> Wert in die lokale Zeit.                                 |

> [!NOTE]
> Die <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType>-Methode verhält sich identisch mit der `DateTime.ToLocalTime`-Methode. Er nimmt einen einzelnen Parameter an, der den zu konvertierenden Datums-und Uhrzeitwert ist.

Sie können auch die Zeit in einer bestimmten Zeitzone in die Ortszeit konvertieren, indem Sie die `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType>-Methode verwenden. Diese Vorgehensweise wird im nächsten Abschnitt erläutert.

## <a name="converting-between-any-two-time-zones"></a>Konvertieren zwischen zwei beliebigen Zeitzonen

Sie können zwischen zwei beliebigen Zeitzonen konvertieren, indem Sie eine der `static` beiden folgenden Methoden (`Shared` in Visual Basic) der <xref:System.TimeZoneInfo>-Klasse verwenden:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  Die Parameter dieser Methode sind der zu konvertierende Datums-und Uhrzeitwert, ein `TimeZoneInfo` Objekt, das die Zeitzone des Datums-und Uhrzeitwerts darstellt, und ein `TimeZoneInfo`-Objekt, das die Zeitzone darstellt, in die der Datums-und Uhrzeitwert konvertiert werden soll.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Die Parameter dieser Methode sind der zu konvertierende Datums-und Uhrzeitwert, der Bezeichner für die Zeitzone des Datums-und Uhrzeitwerts und der Bezeichner der Zeitzone, in die der Datums-und Uhrzeitwert konvertiert werden soll.

Beide Methoden erfordern, dass die <xref:System.DateTime.Kind%2A>-Eigenschaft des zu konvertierenden Datums-und Uhrzeitwerts und das <xref:System.TimeZoneInfo> Objekt oder der Zeit Zonen Bezeichner, der die Zeitzone repräsentiert, einander entsprechen. Andernfalls wird eine <xref:System.ArgumentException> ausgelöst. Wenn die `Kind`-Eigenschaft des Datums-und Uhrzeitwerts z. b. `DateTimeKind.Local`ist, wird eine Ausnahme ausgelöst, wenn das `TimeZoneInfo` Objekt, das als Parameter an die-Methode übergeben wurde, nicht gleich `TimeZoneInfo.Local`ist. Eine Ausnahme wird auch ausgelöst, wenn der als Parameter an die Methode übergebene Bezeichner nicht gleich `TimeZoneInfo.Local.Id`ist.

Im folgenden Beispiel wird die <xref:System.TimeZoneInfo.ConvertTime%2A>-Methode verwendet, um von der Hawaii-Standard Zeit in die lokale Uhrzeit zu konvertieren.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Konvertieren von DateTimeOffset-Werten

Datums-und Uhrzeitwerte, die durch <xref:System.DateTimeOffset>-Objekte dargestellt werden, sind nicht vollständig Zeit Zonen fähig, da das-Objekt bei der instanziierten Zeit nicht mit seiner Zeitzone verknüpft ist. In vielen Fällen muss eine Anwendung jedoch einfach nur ein Datum und eine Uhrzeit basierend auf zwei verschiedenen Abweichungen von der UTC konvertieren, nicht basierend auf der Uhrzeit in bestimmten Zeitzonen. Um diese Konvertierung auszuführen, können Sie die <xref:System.DateTimeOffset.ToOffset%2A>-Methode der aktuellen Instanz aufzurufen. Der einzige Parameter der Methode ist der Offset des neuen Datums-und Uhrzeitwerts, der von der Methode zurückgegeben werden soll.

Wenn Datum und Uhrzeit einer Benutzeranforderung für eine Webseite bekannt sind und als Zeichenfolge im Format MM/dd/yyyy hh:mm:ss zzzz serialisiert wurden, konvertiert die folgende `ReturnTimeOnServer`-Methode diesen Datums- und Uhrzeitwert in das Datum und die Uhrzeit des Webservers.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]

Wenn der-Methode die Zeichenfolge "9/1/2007 5:32:07 -05:00", die das Datum und die Uhrzeit in einer Zeitzone von fünf Stunden vor der UTC darstellt, an die-Methode zurückgegeben wird, gibt Sie 9/1/2007 3:32:07 am-07:00 für einen Server zurück, der sich in der US Pacific Standard Time Zone befindet.

Die <xref:System.TimeZoneInfo>-Klasse enthält auch eine Überladung der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>-Methode, die Zeit Zonen Konvertierungen mit <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)>-Werten ausführt. Die Parameter der Methode sind ein <xref:System.DateTimeOffset> Wert und ein Verweis auf die Zeitzone, in die die Uhrzeit konvertiert werden soll. Der Methoden Aufrufwert gibt einen <xref:System.DateTimeOffset> Wert zurück. Die `ReturnTimeOnServer`-Methode im vorherigen Beispiel könnte z. b. wie folgt umgeschrieben werden, um die <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>-Methode aufzurufen.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Siehe auch

- <xref:System.TimeZoneInfo>
- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Suchen der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
