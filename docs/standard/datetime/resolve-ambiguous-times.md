---
title: 'Vorgehensweise: Auflösen mehrdeutiger Zeiten'
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], ambiguous time
- ambiguous time [.NET]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 29a549d519bd3b6c10fef8205b30a07a71f01d1a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817756"
---
# <a name="how-to-resolve-ambiguous-times"></a>Vorgehensweise: Auflösen mehrdeutiger Zeiten

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise während der Umstellung von Sommerzeit in einer Zeitzone auf Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

- Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

- Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

In diesem Thema wird gezeigt, wie eine mehrdeutige Zeit aufgelöst werden kann, indem angenommen wird, dass Sie die Standardzeit der Zeitzone darstellt.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu

1. Mit der- <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> Methode können Sie ermitteln, ob die Zeit mehrdeutig ist.

2. Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit von dem Objekt, das <xref:System.TimeSpan> von der-Eigenschaft der Zeitzone zurückgegeben wird <xref:System.TimeZoneInfo.BaseUtcOffset%2A> .

3. Mit der `static` ( `Shared` in Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A> -Methode können Sie die-Eigenschaft des UTC-Datums-und Uhrzeitwerts <xref:System.DateTime.Kind%2A> auf festlegen <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie eine mehrdeutige Zeit in die UTC konvertiert wird, indem angenommen wird, dass Sie die Standardzeit der lokalen Zeitzone darstellt.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Das Beispiel besteht aus einer Methode mit dem Namen `ResolveAmbiguousTime` , die bestimmt, ob der <xref:System.DateTime> an Sie über gegebene Wert mehrdeutig ist. Wenn der Wert mehrdeutig ist, gibt die Methode einen <xref:System.DateTime> Wert zurück, der die entsprechende UTC-Zeit darstellt. Die-Methode behandelt diese Konvertierung, indem Sie den Wert der-Eigenschaft der lokalen Zeitzone <xref:System.TimeZoneInfo.BaseUtcOffset%2A> von der Ortszeit subtrahieren.

Normalerweise wird eine mehrdeutige Zeit durch Aufrufen der <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> -Methode verarbeitet, um ein Array von <xref:System.TimeSpan> -Objekten abzurufen, die die möglichen UTC-Offsets der mehrdeutigen Zeit enthalten. In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll. Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A> -Eigenschaft gibt den Offset zwischen UTC und der Standardzeit einer Zeitzone zurück.

In diesem Beispiel werden alle Verweise auf die lokale Zeitzone über die-Eigenschaft durchgeführt <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> . die lokale Zeitzone wird nie einer Objektvariablen zugewiesen. Dies ist eine empfohlene Vorgehensweise, da durch einen Aufruf der- <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode alle Objekte ungültig werden, denen die lokale Zeitzone zugewiesen ist.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Der <xref:System> Namespace wird mit der- `using` Anweisung importiert (erforderlich in c#-Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](let-users-resolve-ambiguous-times.md)
