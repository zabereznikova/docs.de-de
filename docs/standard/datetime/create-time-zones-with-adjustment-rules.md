---
title: 'Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75e1867e810090bf35a0dfc7def5785747f94382
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln

Die präzise Zeitzoneninformationen, die von einer Anwendung erforderlich sind möglicherweise nicht in einem bestimmten System verschiedenen Gründen vorhanden sein:

* Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.

* Daten über die Zeitzone wurde geändert oder aus der Registrierung entfernt.

* Genaue Informationen zur zeitzonenanpassungen für einen bestimmten Zeitraum für die historischen keinen für die Zeitzone.

In diesen Fällen rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode, um die Zeitzone, die von der Anwendung benötigt definieren. Die Überladungen dieser Methode können Sie um mit oder ohne Anpassungsregeln eine Zeitzone zu erstellen. Wenn die Zeitzone Sommerzeit unterstützt, können Sie Anpassungen mit einer festen "oder" Gleitkomma Anpassungsregeln definieren. (Definitionen von Begriffen, finden Sie im Abschnitt "Zeitzone Terminology" [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).)

> [!IMPORTANT]
> Benutzerdefinierte Zeitzonen durch Aufrufen von erstellt die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode werden nicht an der Registrierung hinzugefügt. Stattdessen können sie nur über den Objektverweis zurückgegebenes aufgerufen werden der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methodenaufruf.

In diesem Thema wird gezeigt, wie Anpassungsregeln eine Zeitzone erstellt. Um eine Zeitzone erstellen, die nicht über Regeln zur Anpassung der Sommerzeit unterstützt, finden Sie unter [Vorgehensweise: Erstellen Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>So erstellen eine Zeitzone mit Anpassungsregeln

1. Für jede Anpassung (das ist, für die Umstellung von und zurück zur Normalzeit in einem bestimmten Zeitintervall), gehen Sie folgendermaßen vor:

    1. Definieren der Übergang Startzeitpunkt für die Anpassung der Zeitzone.

       Rufen Sie die <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> Methode und übergibt ihn dann ein <xref:System.DateTime> -Wert, der festgelegt, wie lange der Übergang, ein ganzzahliger Wert, der den Monat des Übergangs definiert, ein ganzzahliger Wert, der die Woche definiert, auf dem der Übergang erfolgt, und ein <xref:System.DayOfWeek> Wert, der den Tag der Woche definiert, an dem der Übergang auftritt. Dieser Methodenaufruf instanziiert ein <xref:System.TimeZoneInfo.TransitionTime> Objekt.

    2. Definieren Sie den Übergang Beendigungszeit für die Anpassung der Zeitzone. Rufen Sie dazu die <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> Methode. Dieser Methodenaufruf instanziiert ein zweites <xref:System.TimeZoneInfo.TransitionTime> Objekt.

    3. Rufen Sie die <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> Methode, und übergeben sie die effektive Start- und Enddatum für die Anpassung einer <xref:System.TimeSpan> Objekt, das die Zeitspanne in der Übergang und die beiden definiert <xref:System.TimeZoneInfo.TransitionTime> Objekten, die beim definieren die Übergänge zu und von Sommerzeit Endzeit liegen. Dieser Methodenaufruf instanziiert ein <xref:System.TimeZoneInfo.AdjustmentRule> Objekt.

    4. Weisen Sie die <xref:System.TimeZoneInfo.AdjustmentRule> Objekt, das ein Array von <xref:System.TimeZoneInfo.AdjustmentRule> Objekte.

2. Anzeigename der Zeitzone zu definieren. Der Anzeigename folgt einem Standardformat in der die Zeitzone Offset von Coordinated Universal Time (UTC) in Klammern eingeschlossen und wird gefolgt von einer Zeichenfolge, die die Zeitzone, oder der Orte in der Zeitzone oder eine weitere mindestens eines der Cou identifiziert Osten oder Bereiche in der Zeitzone.

3. Der Name der Standardzeit der Zeitzone zu definieren. Diese Zeichenfolge wird in der Regel auch als Bezeichners der Zeitzone verwendet.

4. Definieren Sie den Namen der Sommerzeit der Zeitzone.

5. Wenn Sie einen anderen Bezeichner als standardmäßigen Namen der Zeitzone verwenden möchten, definieren Sie des Zeitzonenbezeichners.

6. Instanziieren einer <xref:System.TimeSpan> Objekt, das die Zeitzone Offset von UTC definiert. Zeitzonen mit Uhrzeiten, die später als UTC haben einen positiven Offset. Zeitzonen mit Uhrzeiten, die älter als UTC sind haben einen negativen Offset.

7. Rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> Methode zum Instanziieren der neuen Zeitzone.

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert eine Central Normalzeit Zeitzone für den Vereinigten Staaten, die für eine Vielzahl von Zeitintervallen von 1918 auf der aktuellen Anpassungsregeln enthält.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

In diesem Beispiel erstellte Zeitzone hat mehrere Anpassungsregeln. Muss darauf geachtet werden, stellen Sie sicher, dass der effektive Start- und Enddatum einer Anpassungsregel nicht mit den Daten von einem anderen Anpassungsregel überlappen. Wenn eine Überschneidung ist ein <xref:System.InvalidTimeZoneException> ausgelöst wird.

Für veränderliche Anpassungsregeln, wird der Wert 5 zum Übergeben der `week` Parameter von der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> Methode, um anzugeben, dass der Übergang in der letzten Woche eines bestimmten Monats auftritt.

Erstellen Sie das Array von <xref:System.TimeZoneInfo.AdjustmentRule> Objekten, in denen die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> -Methodenaufruf, der Code konnte initialisieren Sie das Array der Größe erforderlich, um die Anzahl von Korrekturen für die Zeitzone erstellt werden. Dieses Codebeispiel ruft stattdessen die <xref:System.Collections.Generic.List%601.Add%2A> Methode, um eine generische jede Anpassungsregel hinzugefügt <xref:System.Collections.Generic.List%601> Auflistung von <xref:System.TimeZoneInfo.AdjustmentRule> Objekte. Der Code ruft dann die <xref:System.Collections.Generic.List%601.CopyTo%2A> Methode, um die Elemente dieser Auflistung in das Array zu kopieren.

Das Beispiel verwendet außerdem die <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> Methode, um feste Datumsangaben Anpassungen zu definieren. Dies ist vergleichbar mit einem Aufruf der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> -Methode, mit dem Unterschied, dass die It nur die Zeit, Monat und Tag der Übergang Parameter erfordert.

Im Beispiel kann mit den folgenden Code getestet werden:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

* Dem Projekt ein Verweis auf "System.Core.dll" hinzugefügt werden.

* Dass die folgenden Namespaces importiert werden:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
[Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
