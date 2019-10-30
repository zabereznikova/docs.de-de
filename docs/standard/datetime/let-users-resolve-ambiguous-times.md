---
title: 'Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
ms.openlocfilehash: f988616a4b2a5d8202c87e3be3cb23c7f9f1f130
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122279"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a>Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

- Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

- Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

In diesem Thema wird gezeigt, wie ein Benutzer eine mehrdeutige Zeit auflösen kann.

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a>So lassen Sie eine mehrdeutige Zeit vom Benutzer auflösen

1. Holen Sie die Datums- und Uhrzeiteingabe vom Benutzer ein.

2. Ruft die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A>-Methode auf, um zu bestimmen, ob die Zeit mehrdeutig ist.

3. Wenn die Zeit mehrdeutig ist, rufen Sie die <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>-Methode auf, um ein Array mit <xref:System.TimeSpan> Objekten abzurufen. Jedes Element im Array enthält einen UTC-Offset, dem die mehrdeutige Zeit zugeordnet werden kann.

4. Ermöglichen Sie dem Benutzer die Auswahl der gewünschten Abweichung.

5. Sie erhalten das UTC-Datum und die UTC-Uhrzeit durch Subtrahieren der vom Benutzer ausgewählten Abweichung von der lokalen Zeit.

6. Mit der `static`-Methode (`Shared` in Visual Basic .net) <xref:System.DateTime.SpecifyKind%2A>-Methode die <xref:System.DateTime.Kind%2A>-Eigenschaft des UTC-Datums-und Uhrzeitwerts auf <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>festlegen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Benutzer zur Eingabe eines Datums und einer Uhrzeit aufgefordert. Wenn die Angabe mehrdeutig ist, muss der Benutzer die UTC-Zeit auswählen, die der mehrdeutigen Zeit zuzuordnen ist.

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

Der Kern des Beispielcodes verwendet ein Array von <xref:System.TimeSpan>-Objekten, um mögliche Offsets der mehrdeutigen Zeit von UTC anzugeben. Allerdings sind diese Abweichungen für den Benutzer wahrscheinlich eher unverständlich. Um die Bedeutung der Abweichungen zu erläutern, bezeichnet der Code außerdem, ob eine Abweichung die Standardzeit oder die Sommerzeit der lokalen Zeitzone darstellt. Der Code bestimmt, welche Uhrzeit Standard und welche Zeit Sommerzeit ist, indem der Offset mit dem Wert der <xref:System.TimeZoneInfo.BaseUtcOffset%2A>-Eigenschaft verglichen wird. Diese Eigenschaft gibt die Differenz zwischen UTC und der Standardzeit der Zeitzone an.

In diesem Beispiel werden alle Verweise auf die lokale Zeitzone über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>-Eigenschaft erstellt. die lokale Zeitzone wird nie einer Objektvariablen zugewiesen. Dies ist eine empfohlene Vorgehensweise, da durch einen Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>-Methode alle Objekte, denen die lokale Zeitzone zugewiesen ist, ungültig werden.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- , Dass der <xref:System> Namespace mit der `using`-Anweisung importiert werden soll C# (erforderlich im Code).

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Vorgehensweise: Auflösen mehrdeutiger Zeiten](../../../docs/standard/datetime/resolve-ambiguous-times.md)
