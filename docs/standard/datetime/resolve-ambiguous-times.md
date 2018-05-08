---
title: 'Vorgehensweise: Auflösen von mehrdeutigen Zeiten'
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
ms.openlocfilehash: a92081a164d15e5150c582b37c6c688cd15e619e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-resolve-ambiguous-times"></a>Vorgehensweise: Auflösen von mehrdeutigen Zeiten

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

* Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

* Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

In diesem Thema zeigt, wie eine mehrdeutige Zeit durch auflösen, vorausgesetzt, dass es die Standardzeit der Zeitzone darstellt.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu

1. Rufen Sie die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> Methode, um zu bestimmen, ob die Zeit mehrdeutig ist.

2. Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit aus der <xref:System.TimeSpan> von der Zeitzone des zurückgegebenen Objekts <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft.

3. Rufen Sie die `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> -Methode zum Festlegen der UTC Datums- oder Zeitwerts <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie eine mehrdeutige Zeit in UTC konvertiert, vorausgesetzt, dass es die Standardzeit für die lokale Zeitzone darstellt.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Das Beispiel besteht eine Methode namens `ResolveAmbiguousTime` , der bestimmt, ob die <xref:System.DateTime> an sie übergebene Wert ist mehrdeutig. Wenn der Wert nicht eindeutig ist, gibt die Methode eine <xref:System.DateTime> Wert, der die entsprechende UTC-Zeit darstellt. Die Methode führt diese Konvertierung durch Subtrahieren den Wert der lokalen Zeitzone <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft von der Ortszeit.

Normalerweise wird eine mehrdeutige Zeit behandelt, durch Aufrufen der <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> Methode zum Abrufen eines Arrays von <xref:System.TimeSpan> Objekte, die die mehrdeutige Zeit mögliche UTC-offsets. In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll. Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft gibt den Offset zwischen UTC und einer Zeitzone zurück.

In diesem Beispiel werden alle Verweise auf die lokale Zeitzone vorgenommen, durch die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> -Eigenschaft, die lokale Zeit, die Zone wird nie etwas zugewiesen, um eine Objektvariable. Dies ist eine empfohlene Vorgehensweise, da ein Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode werden alle Objekte, die die lokale Zeitzone zugewiesen ist ungültig.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[wie: Auflösen mehrdeutige Zeiten Benutzer können](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
