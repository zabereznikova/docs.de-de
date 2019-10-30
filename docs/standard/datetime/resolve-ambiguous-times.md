---
title: 'Gewusst wie: Auflösen von mehrdeutigen Zeiten'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 0b5b28c588237fb2f7f069aaef06f3f73d5268bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122247"
---
# <a name="how-to-resolve-ambiguous-times"></a>Gewusst wie: Auflösen von mehrdeutigen Zeiten

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

- Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

- Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

In diesem Thema wird gezeigt, wie eine mehrdeutige Zeit aufgelöst werden kann, indem angenommen wird, dass Sie die Standardzeit der Zeitzone darstellt.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu

1. Ruft die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A>-Methode auf, um zu bestimmen, ob die Zeit mehrdeutig ist.

2. Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit von dem <xref:System.TimeSpan> Objekt, das von der <xref:System.TimeZoneInfo.BaseUtcOffset%2A>-Eigenschaft der Zeitzone zurückgegeben wird.

3. Mit der `static`-Methode (`Shared` in Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A>-Methode die <xref:System.DateTime.Kind%2A>-Eigenschaft des UTC-Datums-und Uhrzeitwerts auf <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>festlegen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie eine mehrdeutige Zeit in die UTC konvertiert wird, indem angenommen wird, dass Sie die Standardzeit der lokalen Zeitzone darstellt.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Das Beispiel besteht aus einer Methode mit dem Namen `ResolveAmbiguousTime`, die bestimmt, ob der an Sie über gegebene <xref:System.DateTime> Wert mehrdeutig ist. Wenn der Wert mehrdeutig ist, gibt die Methode einen <xref:System.DateTime> Wert zurück, der die entsprechende UTC-Zeit darstellt. Die-Methode behandelt diese Konvertierung, indem der Wert der <xref:System.TimeZoneInfo.BaseUtcOffset%2A>-Eigenschaft der lokalen Zeitzone von der Ortszeit subtrahieren.

Normalerweise wird eine mehrdeutige Zeit durch Aufrufen der <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>-Methode verarbeitet, um ein Array von <xref:System.TimeSpan> Objekten abzurufen, die die möglichen UTC-Offsets der mehrdeutigen Zeit enthalten. In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll. Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A>-Eigenschaft gibt den Offset zwischen UTC und der Standardzeit einer Zeitzone zurück.

In diesem Beispiel werden alle Verweise auf die lokale Zeitzone über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>-Eigenschaft erstellt. die lokale Zeitzone wird nie einer Objektvariablen zugewiesen. Dies ist eine empfohlene Vorgehensweise, da durch einen Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>-Methode alle Objekte, denen die lokale Zeitzone zugewiesen ist, ungültig werden.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- , Dass der <xref:System> Namespace mit der `using`-Anweisung importiert werden soll C# (erforderlich im Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Vorgehensweise: Auflösen mehrdeutiger Zeiten durch den Benutzer](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
