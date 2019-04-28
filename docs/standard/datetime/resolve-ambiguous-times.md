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
ms.openlocfilehash: aae3e5145d2fa85cd55fc5b1288ef4aaa0fef48f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796408"
---
# <a name="how-to-resolve-ambiguous-times"></a>Vorgehensweise: Auflösen mehrdeutiger Zeiten

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

* Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

* Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

In diesem Thema wird gezeigt, wie Sie eine mehrdeutige Zeit durch auflösen, vorausgesetzt, dass er die Standardzeit der Zeitzone darstellt.

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu

1. Rufen Sie die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> Methode, um zu bestimmen, ob die Zeit mehrdeutig ist.

2. Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit aus der <xref:System.TimeSpan> von der Standardzeit der Zeitzone zurückgegebenen Objekts <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft.

3. Rufen Sie die `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> Methode zum Festlegen des UTC Datums- / Uhrzeitwerts <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie eine mehrdeutige Zeit in UTC, indem konvertiert werden, vorausgesetzt, dass er die Standardzeit für die lokale Zeitzone darstellt.

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

Das Beispiel besteht aus einer Methode namens `ResolveAmbiguousTime` , der bestimmt, ob die <xref:System.DateTime> übergebenen Wert ist nicht eindeutig. Wenn der Wert mehrdeutig ist, gibt die Methode eine <xref:System.DateTime> -Wert, der die entsprechende UTC-Zeit darstellt. Die Methode führt diese Konvertierung durch Subtrahieren den Wert der lokalen Zeitzone <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft von der Ortszeit.

Normalerweise erfolgt eine mehrdeutige Zeit durch Aufrufen der <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> Methode zum Abrufen einer Gruppe von <xref:System.TimeSpan> offsets von Objekten, die möglichen UTC der mehrdeutigen Zeit enthalten. In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet werden soll. Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft gibt den Offset zwischen UTC und der Standardzeit einer Zeitzone zurück.

In diesem Beispiel erfolgen alle Verweise auf die lokale Zeitzone über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> -Eigenschaft, die lokale Zeit, die Zone wird nie einer Objektvariablen zugewiesen. Dies ist eine empfohlene Vorgehensweise, da ein Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> -Methode ungültig macht, alle Objekte, die die lokale Zeitzone zugewiesen ist.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dass das Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Vorgehensweise: Können Sie Benutzer auflösen mehrdeutiger Zeiten](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)
