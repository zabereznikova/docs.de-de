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
ms.openlocfilehash: 6ae739d3c5dd233c2129950666846979edfba370
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106677"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln

Die genauen Zeitzoneninformationen, die von einer Anwendung benötigt werden, sind möglicherweise aus verschiedenen Gründen nicht auf einem bestimmten System vorhanden:

- Die Zeitzone wurde nie in der Registrierung des lokalen Systems definiert.

- Daten über die Zeitzone wurden geändert oder aus der Registrierung entfernt.

- Die Zeitzone weist keine genauen Informationen zu Zeit Zonen Anpassungen für einen bestimmten historischen Zeitraum auf.

In diesen Fällen können Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methode zum Definieren der Zeitzone, die für Ihre Anwendung erforderlich ist, aufzurufen. Sie können die über Ladungen dieser Methode verwenden, um eine Zeitzone mit oder ohne Anpassungsregeln zu erstellen. Wenn die Zeitzone die Sommerzeit unterstützt, können Sie Anpassungen mit festgelegten oder Gleit Komma Anpassungsregeln definieren. (Informationen zu Definitionen dieser Begriffe finden Sie im Abschnitt "Zeit Zonen Terminologie" unter [Übersicht über](../../../docs/standard/datetime/time-zone-overview.md)die Zeitzone.)

> [!IMPORTANT]
> Benutzerdefinierte Zeitzonen, die durch den <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Aufruf der-Methode erstellt wurden, werden nicht zur Registrierung hinzugefügt. Stattdessen kann nur über den Objekt Verweis darauf zugegriffen werden, der durch den <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methoden-Befehl zurückgegeben wird.

In diesem Thema wird gezeigt, wie Sie eine Zeitzone mit Anpassungsregeln erstellen. Informationen zum Erstellen einer Zeitzone, die keine Anpassungsregeln für die Sommerzeit unterstützt [, finden Sie unter Gewusst wie: Erstellen Sie Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>So erstellen Sie eine Zeitzone mit Gleit Komma Anpassungsregeln

1. Gehen Sie für jede Anpassung (d. h. für jeden Übergang von und zurück zur Standardzeit über ein bestimmtes Zeitintervall) wie folgt vor:

    1. Hiermit wird die Anfangs Übergangszeit für die Zeit Zonen Anpassung definiert.

       Sie müssen die <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> -Methode aufruft und ihr einen <xref:System.DateTime> Wert übergeben, der die Zeit des Übergangs definiert, einen ganzzahligen Wert, der den Monat des Übergangs definiert, einen ganzzahligen Wert, der die Woche definiert, in <xref:System.DayOfWeek> der der Übergang erfolgt, und eine der-Wert, der den Wochentag definiert, an dem der Übergang auftritt. Dieser Methoden aufzurufende instanziiert ein <xref:System.TimeZoneInfo.TransitionTime> -Objekt.

    2. Hiermit wird die Endzeit für die Endzeit der Zeit Zonen Anpassung definiert. Hierfür ist ein weiterer Rückruf der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> -Methode erforderlich. Dieser Methoden aufzurufen instanziiert ein <xref:System.TimeZoneInfo.TransitionTime> zweites-Objekt.

    3. Wenden Sie <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> die-Methode an, und übergeben Sie Ihr das effektive Start-und Enddatum der Anpassung, ein <xref:System.TimeSpan> -Objekt, das die Zeitspanne im Übergang <xref:System.TimeZoneInfo.TransitionTime> definiert, und die beiden-Objekte, die definieren, wann der Übergang zu und von der Sommerzeit stattfindet. die Zeit ist aufgetreten. Dieser Methoden aufzurufende instanziiert ein <xref:System.TimeZoneInfo.AdjustmentRule> -Objekt.

    4. Weisen Sie <xref:System.TimeZoneInfo.AdjustmentRule> das-Objekt einem Array <xref:System.TimeZoneInfo.AdjustmentRule> von-Objekten zu.

2. Hiermit wird der Anzeige Name der Zeitzone definiert. Der Anzeige Name folgt einem Recht standardmäßigen Format, in dem der Offset der Zeitzone von der koordinierten Weltzeit (UTC) in Klammern eingeschlossen wird, gefolgt von einer Zeichenfolge, die die Zeitzone, eine oder mehrere Städte in der Zeitzone oder eine oder mehrere der Orte (cou) identifiziert. ntries oder Regionen in der Zeitzone.

3. Hiermit wird der Name der Standardzeit der Zeitzone definiert. In der Regel wird diese Zeichenfolge auch als Bezeichner der Zeitzone verwendet.

4. Hiermit wird der Name der Sommerzeit der Zeitzone definiert.

5. Wenn Sie einen anderen Bezeichner als den Standardnamen der Zeitzone verwenden möchten, definieren Sie den Zeit Zonen Bezeichner.

6. Instanziieren Sie <xref:System.TimeSpan> ein-Objekt, das den Zeit Zonen Offset von UTC definiert. Zeitzonen mit Uhrzeiten, die später als UTC liegen, haben einen positiven Offset. Zeitzonen mit Zeiten, die älter sind als UTC, haben einen negativen Offset.

7. Ruft die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> -Methode auf, um die neue Zeitzone zu instanziieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine zentrale Standard Zeitzone für die USA definiert, die Anpassungsregeln für eine Vielzahl von Zeitintervallen von 1918 bis zum aktuellen umfasst.

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

Die in diesem Beispiel erstellte Zeitzone verfügt über mehrere Anpassungsregeln. Es muss darauf geachtet werden, dass sich das effektive Start-und Enddatum einer beliebigen Anpassungs Regel nicht mit den Datumsangaben einer anderen Anpassungs Regel überschneidet. Wenn eine Überlappung vorliegt, wird <xref:System.InvalidTimeZoneException> eine ausgelöst.

Für Gleit Komma Anpassungsregeln wird der Wert 5 an den `week` -Parameter <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> der-Methode übergeben, um anzugeben, dass der Übergang in der letzten Woche eines bestimmten Monats erfolgt.

Beim Erstellen des Arrays von <xref:System.TimeZoneInfo.AdjustmentRule> -Objekten, die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> im Methodenaufruf verwendet werden sollen, könnte der Code das Array mit der Größe initialisieren, die für die Anzahl der für die Zeitzone zu erstellenden Anpassungen erforderlich ist. Stattdessen wird in diesem Codebeispiel die <xref:System.Collections.Generic.List%601.Add%2A> -Methode aufgerufen, um jede Anpassungs Regel einer <xref:System.Collections.Generic.List%601> generischen <xref:System.TimeZoneInfo.AdjustmentRule> Auflistung von-Objekten hinzuzufügen. Der Code ruft dann die <xref:System.Collections.Generic.List%601.CopyTo%2A> -Methode auf, um die Elemente dieser Auflistung in das Array zu kopieren.

Im Beispiel wird auch die <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> -Methode verwendet, um Anpassungen fester Datumsangaben zu definieren. Dies ähnelt dem Aufrufen der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> -Methode, mit der Ausnahme, dass Sie nur die Zeit, den Monat und den Tag der Übergangs Parameter erfordert.

Das Beispiel kann mithilfe von Code wie dem folgenden getestet werden:

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Für dieses Beispiel benötigen Sie Folgendes:

- Die folgenden Namespaces werden importiert:

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>Siehe auch

- [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
- [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
- [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
