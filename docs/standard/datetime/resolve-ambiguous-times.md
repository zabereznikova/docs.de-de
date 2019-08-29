---
title: 'Vorgehensweise: Auflösen mehrdeutiger Zeiten'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e98d5d8240492ca30da2825b72277d7a35f97f6
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106781"
---
# <a name="how-to-resolve-ambiguous-times"></a>Vorgehensweise: Auflösen mehrdeutiger Zeiten

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

- Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

- Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

In diesem Thema wird gezeigt, wie eine mehrdeutige Zeit aufgelöst werden kann, indem angenommen wird, dass Sie die Standardzeit der Zeitzone darstellt.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu

1. Mit der <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> -Methode können Sie ermitteln, ob die Zeit mehrdeutig ist.

2. Wenn die Zeit mehrdeutig ist, subtrahieren Sie <xref:System.TimeSpan> die Zeit von dem Objekt, das <xref:System.TimeZoneInfo.BaseUtcOffset%2A> von der-Eigenschaft der Zeitzone zurückgegeben wird.

3. Mit der `static` (`Shared` in Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A> -Methode können Sie die-Eigenschaft des UTC- <xref:System.DateTime.Kind%2A> Datums- <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>und Uhrzeitwerts auf festlegen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie eine mehrdeutige Zeit in die UTC konvertiert wird, indem angenommen wird, dass Sie die Standardzeit der lokalen Zeitzone darstellt.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Das Beispiel besteht aus einer Methode mit `ResolveAmbiguousTime` dem Namen, die <xref:System.DateTime> bestimmt, ob der an Sie über gegebene Wert mehrdeutig ist. Wenn der Wert mehrdeutig ist, gibt die Methode <xref:System.DateTime> einen Wert zurück, der die entsprechende UTC-Zeit darstellt. Die-Methode behandelt diese Konvertierung, indem Sie den Wert der- <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft der lokalen Zeitzone von der Ortszeit subtrahieren.

Normalerweise wird eine mehrdeutige Zeit durch Aufrufen der <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> -Methode verarbeitet, um ein <xref:System.TimeSpan> Array von-Objekten abzurufen, die die möglichen UTC-Offsets der mehrdeutigen Zeit enthalten. In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll. Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A> -Eigenschaft gibt den Offset zwischen UTC und der Standardzeit einer Zeitzone zurück.

In diesem Beispiel werden alle Verweise auf die lokale Zeitzone über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> -Eigenschaft durchgeführt. die lokale Zeitzone wird nie einer Objektvariablen zugewiesen. Dies ist eine empfohlene Vorgehensweise, da durch einen <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Aufruf der-Methode alle Objekte ungültig werden, denen die lokale Zeitzone zugewiesen ist.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Der <xref:System> Namespace, der mit der `using` -Anweisung importiert werden soll C# (erforderlich im Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Vorgehensweise: Auflösen mehrdeutiger Zeiten durch den Benutzer](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
