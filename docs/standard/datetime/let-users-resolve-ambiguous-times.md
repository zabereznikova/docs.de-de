---
title: 'Vorgehensweise: ermöglicht Benutzern, Auflösen von mehrdeutigen Zeiten'
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4083871dd97a36529351aacbdcd39980bdde74a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572826"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a>Vorgehensweise: ermöglicht Benutzern, Auflösen von mehrdeutigen Zeiten

Eine mehrdeutige Zeit ist eine Zeit, die mehreren koordinierten Weltzeiten (UTC) zugeordnet werden kann. Dies ist der Fall, wenn die Uhrzeit umgestellt wird, beispielsweise während des Übergangs von der Sommerzeit einer Zeitzone auf die Standardzeit. Bei der Verarbeitung einer mehrdeutigen Zeit haben Sie eine der folgenden Möglichkeiten:

* Wenn die mehrdeutige Zeit ein vom Benutzer eingegebenes Datenelement ist, können Sie es dem Benutzer überlassen, die Mehrdeutigkeit aufzulösen.

* Treffen Sie eine Annahme darüber, wie die Zeit UTC zuzuordnen ist. Beispielsweise können Sie davon ausgehen, dass eine mehrdeutige Zeit immer in der Standardzeit der Zeitzone ausgedrückt wird.

In diesem Thema wird gezeigt, wie damit einen Benutzer eine mehrdeutige Zeit aufgelöst wird.

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a>So lassen Sie eine mehrdeutige Zeit vom Benutzer auflösen

1. Holen Sie die Datums- und Uhrzeiteingabe vom Benutzer ein.

2. Rufen Sie die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> Methode, um zu bestimmen, ob die Zeit mehrdeutig ist.

3. Wenn die Zeit mehrdeutig ist, rufen Sie die <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> Methode zum Abrufen eines Arrays von <xref:System.TimeSpan> Objekte. Jedes Element im Array enthält einen UTC-zeitverschiebung, die die mehrdeutige Zeit zuordnen kann.

4. Ermöglichen Sie dem Benutzer die Auswahl der gewünschten Abweichung.

5. Sie erhalten das UTC-Datum und die UTC-Uhrzeit durch Subtrahieren der vom Benutzer ausgewählten Abweichung von der lokalen Zeit.

6. Rufen Sie die `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> -Methode zum Festlegen der UTC Datums- oder Zeitwerts <xref:System.DateTime.Kind%2A> Eigenschaft <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Benutzer zur Eingabe eines Datums und einer Uhrzeit aufgefordert. Wenn die Angabe mehrdeutig ist, muss der Benutzer die UTC-Zeit auswählen, die der mehrdeutigen Zeit zuzuordnen ist.

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

Der Kern des Beispielcodes verwendet ein Array von <xref:System.TimeSpan> Objekte, um mögliche Offsets der mehrdeutigen Zeit von UTC anzugeben. Allerdings sind diese Abweichungen für den Benutzer wahrscheinlich eher unverständlich. Um die Bedeutung der Abweichungen zu erläutern, bezeichnet der Code außerdem, ob eine Abweichung die Standardzeit oder die Sommerzeit der lokalen Zeitzone darstellt. Im Code wird ermittelt, welche Zeit standardmäßig vorhanden sind und welche Zeit Sommerzeit durch Vergleichen des Offsets mit dem Wert von der <xref:System.TimeZoneInfo.BaseUtcOffset%2A> Eigenschaft. Diese Eigenschaft gibt die Differenz zwischen UTC und der Standardzeit der Zeitzone an.

In diesem Beispiel werden alle Verweise auf die lokale Zeitzone vorgenommen, durch die <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> -Eigenschaft, die lokale Zeit, die Zone wird nie etwas zugewiesen, um eine Objektvariable. Dies ist eine empfohlene Vorgehensweise, da ein Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> Methode werden alle Objekte, die die lokale Zeitzone zugewiesen ist ungültig.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die <xref:System> Namespace importiert werden, mit der `using` -Anweisung (in C#-Code erforderlich).

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[wie: Auflösen von mehrdeutigen Zeiten](../../../docs/standard/datetime/resolve-ambiguous-times.md)
