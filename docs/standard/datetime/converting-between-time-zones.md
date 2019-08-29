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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b78e3985169954d71b479aa2e8a034f61afc01
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106971"
---
# <a name="converting-times-between-time-zones"></a>Konvertieren von Uhrzeiten zwischen Zeitzonen

Es wird immer wichtiger, dass Anwendungen, die mit Daten und Uhrzeiten arbeiten, Unterschiede zwischen Zeitzonen verarbeiten können. Eine Anwendung kann nicht mehr davon ausgehen, dass alle Uhrzeiten in der Ortszeit ausgedrückt werden können. Dies ist die Zeit, <xref:System.DateTime> die in der Struktur verfügbar ist. Eine Webseite beispielsweise, die die aktuelle Uhrzeit für die Ostküste der USA anzeigt, wird für Kunden in Ostasien an Glaubwürdigkeit verlieren. In diesem Thema wird erläutert, wie Sie Uhrzeiten von einer Zeitzone in eine andere konvertieren können, und <xref:System.DateTimeOffset> wie Sie Werte mit eingeschränkter Zeit Zonen Bekanntheit konvertieren.

## <a name="converting-to-coordinated-universal-time"></a>Konvertieren in die koordinierte Weltzeit

Die koordinierte Weltzeit (UTC, Coordinated Universal Time) ist ein auf der Atomzeit basierender, höchst präziser Zeitstandard. Die Zeitzonen der Welt werden als positive oder negative Abweichungen von der UTC ausgedrückt. Daher ist die UTC sozusagen eine zeitzonenfreie bzw. zeitzonenneutrale Zeit. Die Verwendung der UTC wird empfohlen, wenn die computerübergreifende Portabilität von Datum und Uhrzeit von großer Bedeutung ist. (Ausführliche Informationen und weitere bewährte Methoden zum Verwenden von Datums-und Uhrzeitangaben finden Sie unter [Programmieren bewährter Methoden mithilfe von DateTime in der .NET Framework](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10)).) Durch Konvertieren einzelner Zeitzonen in die UTC lassen sich Zeiten einfach miteinander vergleichen.

> [!NOTE]
> Sie können auch eine <xref:System.DateTimeOffset> Struktur serialisieren, um einen bestimmten Zeitpunkt eindeutig darzustellen. Da <xref:System.DateTimeOffset> -Objekte einen Datums-und Uhrzeitwert zusammen mit dem Offset von der UTC speichern, stellen Sie immer einen bestimmten Zeitpunkt in Beziehung zu UTC dar.

Die einfachste Möglichkeit, eine Uhrzeit in die UTC zu konvertieren, besteht `static` darin`Shared` , die- <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> Methode (in Visual Basic) aufzurufen. Die genaue Konvertierung, die von der-Methode durchgeführt wird, `dateTime` hängt vom <xref:System.DateTime.Kind%2A> Wert der-Eigenschaft des-Parameters ab, wie in der folgenden Tabelle gezeigt.

| `DateTime.Kind`            | Umwandeln                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | Konvertiert die lokale Zeit in die UTC.                                                    |
| `DateTimeKind.Unspecified` | Nimmt an, dass der `dateTime`-Parameter die lokale Zeit angibt, und konvertiert die lokale Zeit in die UTC. |
| `DateTimeKind.Utc`         | Gibt den `dateTime`-Parameter unverändert zurück.                                    |

Der folgende Code konvertiert die aktuelle lokale Zeit in die UTC und zeigt das Ergebnis in der Konsole an.

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

Wenn der Datums-und Uhrzeitwert weder die Ortszeit noch UTC darstellt, gibt die <xref:System.DateTime.ToUniversalTime%2A> Methode wahrscheinlich ein falsches Ergebnis zurück. Sie können jedoch die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> -Methode verwenden, um das Datum und die Uhrzeit aus einer angegebenen Zeitzone zu konvertieren. (Ausführliche Informationen zum Abrufen eines <xref:System.TimeZoneInfo> -Objekts, das die Ziel Zeitzone darstellt, finden Sie untersuchen [der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) Im folgenden Code wird die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> -Methode verwendet, um die Eastern Standard Time in die UTC zu konvertieren.

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

Beachten Sie, dass diese Methode <xref:System.ArgumentException> einen auslöst <xref:System.DateTime> , wenn <xref:System.DateTime.Kind%2A> die-Eigenschaft des-Objekts und die Zeitzone nicht übereinstimmen. Ein Konflikt tritt auf, wenn <xref:System.DateTime.Kind%2A> die- <xref:System.DateTimeKind.Local?displayProperty=nameWithType> Eigenschaft ist <xref:System.TimeZoneInfo> , das-Objekt jedoch nicht die lokale Zeitzone darstellt, oder <xref:System.DateTime.Kind%2A> wenn die <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> -Eigenschaft <xref:System.TimeZoneInfo> ist, aber das <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>-Objekt nicht gleich ist.

Alle diese Methoden übernehmen <xref:System.DateTime> Werte als Parameter und geben einen <xref:System.DateTime> Wert zurück. Für <xref:System.DateTimeOffset> -Werte verfügt <xref:System.DateTimeOffset> die-Struktur <xref:System.DateTimeOffset.ToUniversalTime%2A> über eine-Instanzmethode, die das Datum und die Uhrzeit der aktuellen Instanz in die UTC konvertiert. Im folgenden Beispiel wird die <xref:System.DateTimeOffset.ToUniversalTime%2A> -Methode aufgerufen, um eine lokale Uhrzeit und einige andere Uhrzeiten in die koordinierte Weltzeit (UTC) zu konvertieren.

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>Konvertieren der UTC in eine festgelegte Zeitzone

Informationen zum Konvertieren der UTC in eine lokale Zeit finden Sie im folgenden Abschnitt "Konvertieren der UTC in eine lokale Zeit". Um die UTC in die Zeit in einer von Ihnen festgelegten Zeitzone zu konvertieren, <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> müssen Sie die-Methode aufzurufen. Die Methode akzeptiert zwei Parameter:

- Die zu konvertierende UTC. Dabei muss es sich <xref:System.DateTime> um einen <xref:System.DateTime.Kind%2A> Wert handeln, dessen `Unspecified` - `Utc`Eigenschaft auf oder festgelegt ist.

- Die Zeitzone, in die die UTC konvertiert werden soll.

Der folgende Code konvertiert die UTC in die Central Standard Time.

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>Konvertieren der UTC in eine lokale Zeit

Um die UTC in die lokale Zeit zu konvertieren <xref:System.DateTime.ToLocalTime%2A> , müssen Sie <xref:System.DateTime> die-Methode des-Objekts aufzurufen, dessen Zeit Sie konvertieren möchten. Das genaue Verhalten der-Methode hängt vom Wert der- <xref:System.DateTime.Kind%2A> Eigenschaft des-Objekts ab, wie in der folgenden Tabelle gezeigt.

| `DateTime.Kind`            | Umwandeln                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | Gibt den <xref:System.DateTime> Wert unverändert zurück.                                      |
| `DateTimeKind.Unspecified` | Geht davon aus <xref:System.DateTime> , dass der Wert UTC ist, und konvertiert die UTC in die lokale Zeit. |
| `DateTimeKind.Utc`         | Konvertiert den <xref:System.DateTime> Wert in die lokale Zeit.                                 |

> [!NOTE]
> Die <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> -Methode verhält sich identisch mit `DateTime.ToLocalTime` der-Methode. Er nimmt einen einzelnen Parameter an, der den zu konvertierenden Datums-und Uhrzeitwert ist.

Mithilfe der `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> -Methode können Sie auch die Zeit in einer bestimmten Zeitzone in lokale Zeit konvertieren. Diese Vorgehensweise wird im nächsten Abschnitt erläutert.

## <a name="converting-between-any-two-time-zones"></a>Konvertieren zwischen zwei beliebigen Zeitzonen

Sie können zwischen zwei beliebigen Zeitzonen konvertieren, indem Sie eine der beiden `static` folgenden Methoden (`Shared` in <xref:System.TimeZoneInfo> Visual Basic) der-Klasse verwenden:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  Die Parameter dieser Methode sind der zu konvertierende Datums-und Uhrzeitwert, ein `TimeZoneInfo` -Objekt, das die Zeitzone des Datums-und Uhrzeitwerts darstellt, und ein `TimeZoneInfo` -Objekt, das die Zeitzone darstellt, in die der Datums-und Uhrzeitwert konvertiert werden soll.

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  Die Parameter dieser Methode sind der zu konvertierende Datums-und Uhrzeitwert, der Bezeichner für die Zeitzone des Datums-und Uhrzeitwerts und der Bezeichner der Zeitzone, in die der Datums-und Uhrzeitwert konvertiert werden soll.

Beide Methoden erfordern, dass <xref:System.DateTime.Kind%2A> die-Eigenschaft des zu konvertierenden Datums-und Uhrzeitwerts und der Objekt-oder Zeit Zonen Bezeichner, der <xref:System.TimeZoneInfo> die Zeitzone darstellt, einander entsprechen. Andernfalls wird eine <xref:System.ArgumentException> ausgelöst. Wenn `Kind` beispielsweise die-Eigenschaft des Datums-und Uhrzeitwerts ist `DateTimeKind.Local`, wird eine-Ausnahme ausgelöst `TimeZoneInfo` , wenn das Objekt, das als `TimeZoneInfo.Local`Parameter an die-Methode übergeben wurde, nicht gleich ist. Eine Ausnahme wird auch ausgelöst, `TimeZoneInfo.Local.Id`wenn der als Parameter an die Methode übergebene Bezeichner nicht gleich ist.

Im folgenden Beispiel wird die <xref:System.TimeZoneInfo.ConvertTime%2A> -Methode verwendet, um von der Hawaii-Standard Zeit in die lokale Uhrzeit zu konvertieren.

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>Konvertieren von DateTimeOffset-Werten

Datums-und Uhrzeitwerte <xref:System.DateTimeOffset> , die durch-Objekte dargestellt werden, sind nicht vollständig Zeit Zonen fähig, da das-Objekt zu dem Zeitpunkt, zu dem er instanziiert wird, von der Zeitzone getrennt wird. In vielen Fällen muss eine Anwendung jedoch einfach nur ein Datum und eine Uhrzeit basierend auf zwei verschiedenen Abweichungen von der UTC konvertieren, nicht basierend auf der Uhrzeit in bestimmten Zeitzonen. Um diese Konvertierung auszuführen, können Sie die-Methode der aktuellen <xref:System.DateTimeOffset.ToOffset%2A> Instanz von aufzurufen. Der einzige Parameter der Methode ist der Offset des neuen Datums-und Uhrzeitwerts, der von der Methode zurückgegeben werden soll.

Wenn Datum und Uhrzeit einer Benutzeranforderung für eine Webseite bekannt sind und als Zeichenfolge im Format MM/dd/yyyy hh:mm:ss zzzz serialisiert wurden, konvertiert die folgende `ReturnTimeOnServer`-Methode diesen Datums- und Uhrzeitwert in das Datum und die Uhrzeit des Webservers.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

Beispiel: An diese Methode wird die Zeichenfolge „9/1/2007 5:32:07 -05:00“ übergeben. Diese stellt das Datum und die Uhrzeit in einer Zeitzone dar, die fünf Stunden vor der UTC liegt. In diesem Fall gibt die Methode den Wert „9/1/2007 3:32:07 AM -07:00“ zurück, wenn sich der Server in der Zeitzone „Pacific Standard Time“ (USA) ausgeführt wird.

Die <xref:System.TimeZoneInfo> -Klasse enthält auch eine <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> Überladung der-Methode, die Zeit Zonen <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> Konvertierungen mit-Werten ausführt. Die Parameter der Methode sind ein <xref:System.DateTimeOffset> Wert und ein Verweis auf die Zeitzone, in die die Uhrzeit konvertiert werden soll. Der Methoden Aufrufwert <xref:System.DateTimeOffset> gibt einen-Wert zurück. Die `ReturnTimeOnServer` -Methode im vorherigen Beispiel könnte z. b. wie folgt umgeschrieben werden, <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> um die-Methode aufzurufen.

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>Siehe auch

- <xref:System.TimeZoneInfo>
- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Suchen der in einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
