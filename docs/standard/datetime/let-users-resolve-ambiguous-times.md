---
title: 'Vorgehensweise: Auflösen mehrdeutiger Zeiten durch den Benutzer'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
ms.openlocfilehash: ac723738d80a2f686a5fcaf279cec791b3c58619
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281582"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a>Vorgehensweise: Auflösen mehrdeutiger Zeiten durch den Benutzer

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise während der Umstellung von Sommerzeit in einer Zeitzone auf Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

- Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

- Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

In diesem Thema wird gezeigt, wie ein Benutzer eine mehrdeutige Zeit auflösen kann.

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a>So lassen Sie eine mehrdeutige Zeit vom Benutzer auflösen

1. Holen Sie die Datums- und Uhrzeiteingabe vom Benutzer ein.

2. Mit der- <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> Methode können Sie ermitteln, ob die Zeit mehrdeutig ist.

3. Wenn die Zeit mehrdeutig ist, rufen <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> Sie die-Methode auf, um ein Array von- <xref:System.TimeSpan> Objekten abzurufen. Jedes Element im Array enthält einen UTC-Offset, dem die mehrdeutige Zeit zugeordnet werden kann.

4. Ermöglichen Sie dem Benutzer die Auswahl der gewünschten Abweichung.

5. Sie erhalten das UTC-Datum und die UTC-Uhrzeit durch Subtrahieren der vom Benutzer ausgewählten Abweichung von der lokalen Zeit.

6. Mit der `static` ( `Shared` in Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A> -Methode können Sie die-Eigenschaft des UTC-Datums-und Uhrzeitwerts <xref:System.DateTime.Kind%2A> auf festlegen <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Benutzer zur Eingabe eines Datums und einer Uhrzeit aufgefordert. Wenn die Angabe mehrdeutig ist, muss der Benutzer die UTC-Zeit auswählen, die der mehrdeutigen Zeit zuzuordnen ist.

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

Der Kern des Beispielcodes verwendet ein Array von- <xref:System.TimeSpan> Objekten, um mögliche Offsets der mehrdeutigen Zeit von UTC anzugeben. Allerdings sind diese Abweichungen für den Benutzer wahrscheinlich eher unverständlich. Um die Bedeutung der Abweichungen zu erläutern, bezeichnet der Code außerdem, ob eine Abweichung die Standardzeit oder die Sommerzeit der lokalen Zeitzone darstellt. Der Code bestimmt, welche Uhrzeit Standard und welche Zeit Sommerzeit ist, indem der Offset mit dem Wert der-Eigenschaft verglichen wird <xref:System.TimeZoneInfo.BaseUtcOffset%2A> . Diese Eigenschaft gibt die Differenz zwischen UTC und der Standardzeit der Zeitzone an.

In diesem Beispiel werden alle Verweise auf die lokale Zeitzone über die-Eigenschaft durchgeführt <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> . die lokale Zeitzone wird nie einer Objektvariablen zugewiesen. Dies ist eine empfohlene Vorgehensweise, da durch einen Aufruf der- <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode alle Objekte ungültig werden, denen die lokale Zeitzone zugewiesen ist.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Der <xref:System> Namespace wird mit der- `using` Anweisung importiert (erforderlich in c#-Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](index.md)
- [Vorgehensweise: Auflösen mehrdeutiger Zeiten](resolve-ambiguous-times.md)
