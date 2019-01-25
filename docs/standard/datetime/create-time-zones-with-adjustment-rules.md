---
title: 'Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83905c97f37a0e49f6219da47e2f640ecfb8edfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721174"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln

Die genaue Zeitzoneninformationen, die von einer Anwendung erforderlich sind möglicherweise nicht auf einem bestimmten System vorhanden, verschiedene Ursachen haben:

* Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.

* Daten über die Zeitzone wurde geändert oder aus der Registrierung entfernt.

* Genaue Informationen zur zeitzonenanpassungen für einen bestimmten Zeitraum für vergangene keinen für die Zeitzone.

Sie können in diesen Fällen Aufrufen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode, um die Zeitzone, die von der Anwendung benötigten definieren. Sie können die Überladungen dieser Methode verwenden, um mit oder ohne Anpassungsregeln eine Zeitzone zu erstellen. Wenn die Zeitzone Sommerzeit unterstützt, können Sie Anpassungen mit entweder feste "oder" Gleitkomma Anpassungsregeln definieren. (Für die Definitionen dieser Begriffe finden Sie im Abschnitt "Zeitzonenterminologie" [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Benutzerdefinierte Zeitzonen durch Aufrufen von erstellt die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode werden nicht in der Registrierung hinzugefügt. Stattdessen können sie nur über das vom Objektverweis zugegriffen werden die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methodenaufruf.

In diesem Thema veranschaulicht, wie mit Anpassungsregeln eine Zeitzone zu erstellen. Um eine Zeitzone zu erstellen, die keine Anpassungsregeln für die Sommerzeit unterstützt, finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>So erstellen eine Zeitzone mit bewegliche Anpassungsregeln

1. Für jede Regulierung (die ist, dass für die Umstellung von und zurück auf Standardzeit in einem bestimmten Zeitintervall), gehen Sie folgendermaßen vor:

    1. Definieren Sie die Startzeit der Übergang für die Anpassung der Zeitzone.

       Rufen Sie die <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> Methode und übergeben sie einen <xref:System.DateTime> Wert, der die Uhrzeit des Übergangs, ein ganzzahliger Wert, der den Monat des Übergangs definiert, ein ganzzahliger Wert, der die Woche definiert, auf dem der Übergang erfolgt, und ein <xref:System.DayOfWeek> Wert, der den Tag der Woche definiert, an dem der Übergang auftritt. Dieser Methodenaufruf instanziiert ein <xref:System.TimeZoneInfo.TransitionTime> Objekt.

    2. Definieren Sie die Endzeit der Übergang für die Anpassung der Zeitzone. Dies erfordert einen anderen Aufruf der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> Methode. Dieser Methodenaufruf instanziiert ein zweites <xref:System.TimeZoneInfo.TransitionTime> Objekt.

    3. Aufrufen der <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> Methode und übergeben sie die effektive Start- und Enddatum der Anpassung, eine <xref:System.TimeSpan> -Objekt, das die Zeitspanne in den Übergang und die beiden definiert <xref:System.TimeZoneInfo.TransitionTime> Objekte, die beim Definieren der Übergänge zu und von Sommerzeit Zeit auftreten. Dieser Methodenaufruf instanziiert ein <xref:System.TimeZoneInfo.AdjustmentRule> Objekt.

    4. Weisen Sie die <xref:System.TimeZoneInfo.AdjustmentRule> Objekt, das ein Array von <xref:System.TimeZoneInfo.AdjustmentRule> Objekte.

2. Anzeigename der Zeitzone zu definieren. Der Anzeigename folgt ein Standardformat in der der Standardzeit der Zeitzone Offset von Coordinated Universal Time (UTC) wird in Klammern eingeschlossen werden soll, und folgt eine Zeichenfolge, die Zeitzone oder der Städte in der Zeitzone oder eine weitere mindestens die Cou identifiziert Osten oder Regionen, in der Zeitzone.

3. Der Name der Standardzeit der Zeitzone zu definieren. Diese Zeichenfolge wird in der Regel auch als Bezeichner für die Zeitzone verwendet.

4. Definieren Sie den Namen der Sommerzeit der Zeitzone.

5. Wenn Sie einen anderen Bezeichner als standardmäßigen Namen der Zeitzone verwenden möchten, definieren Sie den Zeitzonenbezeichner.

6. Instanziieren einer <xref:System.TimeSpan> -Objekt, das die Zeitzone Offset von UTC definiert. Zeitzonen mit Uhrzeiten, die später als UTC weisen einen positiven Offset. Zeitzonen mit Uhrzeiten, die älter als UTC sind haben einen negativen Offset.

7. Rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> Methode, um die neue Zeitzone zu instanziieren.

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert eine Central Standard Zeitzone für den Vereinigten Staaten, die Anpassungsregeln für eine Vielzahl von Zeitintervallen von 1918 zur Gegenwart enthält.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

Die Zeitzone, die in diesem Beispiel erstellten verfügt über mehrere Regeln zur zeitzonenanpassung berücksichtigt. Muss darauf geachtet werden, stellen Sie sicher, dass das effektive Start- und Enddatum der Anpassungsregel, die alle mit dem Enddatum der Anpassungsregel für eine andere nicht überschneiden. Wenn eine Überlappung, ein <xref:System.InvalidTimeZoneException> ausgelöst.

Für bewegliche Anpassungsregeln, wird der Wert 5 übergeben die `week` Parameter, der die <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> Methode, um anzugeben, dass die Umstellung auf der letzten Woche eines bestimmten Monats auftritt.

Erstellen Sie das Array von <xref:System.TimeZoneInfo.AdjustmentRule> Objekten die Verwendung in der <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> -Methodenaufruf, der Code konnte initialisieren Sie das Array der Größe, die durch die Anzahl der Anpassungen erforderlich sind, für die Zeitzone erstellt werden soll. Dieses Codebeispiel ruft stattdessen die <xref:System.Collections.Generic.List%601.Add%2A> Methode eine generische jede Anpassungsregel hinzuzufügende <xref:System.Collections.Generic.List%601> Auflistung von <xref:System.TimeZoneInfo.AdjustmentRule> Objekte. Der Code ruft dann die <xref:System.Collections.Generic.List%601.CopyTo%2A> Methode, um die Member dieser Auflistung in das Array zu kopieren.

Im Beispiel verwendet auch die <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> Methode, um feste Datumsangaben Anpassungen zu definieren. Dies ist vergleichbar mit einem Aufruf der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> -Methode, mit dem Unterschied, dass die It nur die Zeit, Monat und Tag des Übergangs-Parameter ist erforderlich.

Im Beispiel kann mit folgendem Code getestet werden:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dass das Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
- [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
