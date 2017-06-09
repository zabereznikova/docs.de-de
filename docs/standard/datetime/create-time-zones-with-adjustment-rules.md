---
title: "Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anpassungsregel [.NET Framework]"
  - "Zeitzonen [.NET Framework], und Anpassungsregeln"
  - "Zeitzonen [.NET Framework], Erstellen"
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln
Die genauen Zeitzonendaten, die eine Anwendung benötigt, können aus mehreren Gründen auf einem bestimmten System nicht vorhanden sein:  
  
-   Die Zeitzone wurde zuvor noch nicht in der Registrierung des lokalen Systems definiert.  
  
-   Daten der Zeitzone wurden geändert oder aus der Registrierung entfernt.  
  
-   Die Zeitzone weist keine genauen Informationen über Zeitzonenanpassungen für einen bestimmten historischen Zeitraum auf.  
  
 In diesen Fällen können Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode aufrufen, um die von der Anwendung benötigte Zeitzone zu definieren.  Sie können die Überladungen dieser Methode zum Erstellen einer Zeitzone mit oder ohne Anpassungsregeln verwenden.  Wenn die Zeitzone die Sommerzeit unterstützt, können Sie Anpassungen mit festen oder beweglichen Anpassungsregeln definieren. \(Definitionen dieser Begriffe finden Sie im Abschnitt "Zeitzonenterminologie" unter [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).\)  
  
> [!IMPORTANT]
>  Benutzerdefinierte Zeitzonen, die durch Aufrufen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode erstellt werden, werden nicht zur Registrierung hinzugefügt.  Stattdessen kann nur über den Objektverweis, der vom Aufruf der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode zurückgegeben wird, darauf zugegriffen werden.  
  
 In diesem Thema wird erläutert, wie Sie eine Zeitzone mit Anpassungsregeln erstellen.  Informationen zum Erstellen einer Zeitzone, die keine Anpassungsregeln für die Sommerzeit unterstützt, finden Sie unter [Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).  
  
### So erstellen Sie eine Zeitzone mit beweglichen Anpassungsregeln  
  
1.  Gehen Sie für jede Anpassung \(d. h. für die Umstellung von und zurück auf Normalzeit über ein bestimmtes Zeitintervall\) wie folgt vor:  
  
    1.  Definieren Sie den Beginn der Umstellungszeit für die Zeitzonenanpassung.  
  
         Sie müssen die <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=fullName>\-Methode aufrufen und einen <xref:System.DateTime>\-Wert an sie übergeben, der die Uhrzeit der Umstellung, eine Ganzzahl für den Monat, eine Ganzzahl für die Woche und einen <xref:System.DayOfWeek>\-Wert für den Wochentag der Umstellung definiert.  Dieser Methodenaufruf instanziiert ein <xref:System.TimeZoneInfo.TransitionTime>\-Objekt.  
  
    2.  Definieren Sie das Ende der Umstellungszeit für die Zeitzonenanpassung.  Dies erfordert einen erneuten Aufruf der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=fullName>\-Methode.  Dieser Methodenaufruf instanziiert ein zweites <xref:System.TimeZoneInfo.TransitionTime>\-Objekt.  
  
    3.  Rufen Sie die <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A>\-Methode auf, und übergeben Sie ihr die effektiven Anfangs\- und Enddaten der Anpassung, ein <xref:System.TimeSpan>\-Objekt, das die Dauer der Umstellung angibt, und zwei <xref:System.TimeZoneInfo.TransitionTime>\-Objekte, mit denen definiert wird, wann die Umstellung auf und von Sommerzeit erfolgt.  Dieser Methodenaufruf instanziiert ein <xref:System.TimeZoneInfo.AdjustmentRule>\-Objekt.  
  
    4.  Weisen Sie das <xref:System.TimeZoneInfo.AdjustmentRule>\-Objekt einem Array von <xref:System.TimeZoneInfo.AdjustmentRule>\-Objekten zu.  
  
2.  Definieren Sie den Anzeigenamen der Zeitzone.  Der Anzeigename folgt einem gewissen Standardformat. Hierbei wird der Offset der Zeitzone von der koordinierten Weltzeit \(Coordinated Universal Time, UTC\) in Klammern eingeschlossen, gefolgt von einer Zeichenfolge, die die Zeitzone, einen oder mehrere Orte in der Zeitzone oder ein oder mehrere Länder oder Regionen in der Zeitzone identifiziert.  
  
3.  Definieren Sie den Namen der Normalzeit der Zeitzone.  Diese Zeichenfolge wird normalerweise auch als der Bezeichner der Zeitzone verwendet.  
  
4.  Definieren Sie den Namen der Sommerzeit der Zeitzone.  
  
5.  Wenn Sie einen anderen Bezeichner als den Standardnamen der Zeitzone verwenden möchten, definieren Sie den Zeitzonenbezeichner.  
  
6.  Instanziieren Sie ein <xref:System.TimeSpan>\-Objekt, das den Offset der Zeitzone von UTC definiert.  Zeitzonen mit Uhrzeiten, die nach UTC liegen, weisen einen positiven Offset auf.  Zeitzonen mit Uhrzeiten, die vor UTC liegen, weisen einen negativen Offset auf.  
  
7.  Rufen Sie die [TimeZoneInfo.CreateCustomTimeZone\(String, TimeSpan, String, String, String, TimeZoneInfo.AdjustmentRule\<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=fullName>\-Methode auf, um die neue Zeitzone zu instanziieren.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Central Normalzeit\-Zeitzone für die USA definiert, die Anpassungsregeln für verschiedene Zeitintervalle von 1918 bis heute umfasst.  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
 [!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]  
  
 Die in diesem Beispiel erstellte Zeitzone hat mehrere Anpassungsregeln.  Sie müssen vor allem darauf achten, dass sich die effektiven Anfangs\- und Enddaten einer Anpassungsregel nicht mit denen einer anderen Anpassungsregel überschneiden.  Wenn eine Überschneidung vorliegt, wird eine <xref:System.InvalidTimeZoneException> ausgelöst.  
  
 Bei beweglichen Anpassungsregeln wird der Wert 5 an den `week`\-Parameter der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>\-Methode übergeben, um anzugeben, dass die Umstellung in der letzten Woche eines bestimmten Monats erfolgt.  
  
 Indem das Array von <xref:System.TimeZoneInfo.AdjustmentRule>\-Objekten zur Verwendung mit dem [TimeZoneInfo.CreateCustomTimeZone\(String, TimeSpan, String, String, String, TimeZoneInfo.AdjustmentRule\<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=fullName>\-Methodenaufruf erstellt wird, könnte der Code das Array in der Größe initialisieren, die für die Anzahl der Anpassungsregeln, die für die Zeitzone erstellt werden sollen, notwendig ist.  Dieser Code ruft stattdessen die <xref:System.Collections.Generic.List%601.Add%2A>\-Methode auf, mit der die einzelnen Anpassungsregeln einer allgemeinen <xref:System.Collections.Generic.List%601>\-Auflistung von <xref:System.TimeZoneInfo.AdjustmentRule>\-Objekten hinzugefügt werden.  Im Code wird dann die <xref:System.Collections.Generic.List%601.CopyTo%2A>\-Methode aufgerufen, um die Member dieser Auflistung in das Array zu kopieren.  
  
 Im Beispiel wird außerdem die <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A>\-Methode verwendet, um Anpassungen mit festem Datum zu definieren.  Dies ähnelt dem Aufrufen der <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>\-Methode, wobei jedoch nur die Zeit, der Monat und der Tag der Umstellungsparameter erforderlich sind.  
  
 Das Beispiel kann mit folgendem Code getestet werden:  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
 [!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Dem Projekt muss ein Verweis auf System.Core.dll hinzugefügt werden.  
  
-   Die folgenden Namespaces müssen importiert werden:  
  
     [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
     [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)   
 [Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)