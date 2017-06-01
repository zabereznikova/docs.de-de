---
title: "Konvertieren von Uhrzeiten zwischen Zeitzonen | Microsoft Docs"
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
  - "Konvertieren von Zeiten"
  - "Konvertierung lokaler Zeiten"
  - "Zeitzonen [.NET Framework], Konvertierungen"
  - "Zeiten [.NET Framework], Konvertieren"
  - "UTC-Zeiten, Konvertieren"
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Konvertieren von Uhrzeiten zwischen Zeitzonen
Für Anwendungen, die mit Datumsangaben und Uhrzeiten arbeiten, wird es immer wichtiger, Unterschiede zwischen Zeitzonen verarbeiten zu können.  Eine Anwendung kann nicht länger davon ausgehen, dass alle Uhrzeiten in Ortszeit ausgedrückt werden können, also in der Uhrzeit, die durch die <xref:System.DateTime>\-Struktur festgelegt ist.  So ist beispielsweise eine Webseite, auf der die aktuelle Uhrzeit im Osten der USA angezeigt wird, für einen Benutzer in Ostasien nicht sehr glaubwürdig.  In diesem Thema wird erläutert, wie Uhrzeiten von einer Zeitzone in eine andere konvertiert werden können und wie <xref:System.DateTimeOffset>\-Werte mit eingeschränkter Zeitzonenunterstützung konvertiert werden.  
  
## Konvertieren in koordinierte Weltzeit \(Coordinated Universal Time, UTC\)  
 Bei der koordinierten Weltzeit \(Coordinated Universal Time, UTC\) handelt es sich um einen höchst präzisen Atomzeitstandard.  Die Zeitzonen der Welt werden als positive oder negative Offsets von UTC ausgedrückt.  UTC stellt daher eine Art Zeit dar, die unabhängig von Zeitzonen bzw. neutral ist.  Die Verwendung der UTC\-Zeit wird empfohlen, wenn die Portabilität von Datum und Uhrzeit zwischen Computern wichtig ist. \(Ausführliche Informationen und andere empfohlene Vorgehensweisen mit Datumsangaben und Uhrzeiten, die Sie finden [Codierungs\-Verfahren mithilfe DateTime verwendet in .NET Framework](http://go.microsoft.com/fwlink/?LinkId=92342).\) Durch das Konvertieren einzelner Zeitzonen in UTC wird der Vergleich von Uhrzeiten vereinfacht.  
  
> [!NOTE]
>  Sie können eine <xref:System.DateTimeOffset>\-Struktur auch serialisieren, um einen bestimmten Zeitpunkt eindeutig darzustellen.  Da <xref:System.DateTimeOffset>\-Objekte einen Datums\- und Uhrzeitwert zusammen mit dem Offset von UTC speichern, geben sie stets einen bestimmten Zeitpunkt in Bezug auf UTC an.  
  
 Eine Uhrzeit lässt sich am einfachsten in UTC konvertieren, indem die `static` \(`Shared` in Visual Basic\) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName>\-Methode aufgerufen wird.  Die tatsächlich durch die Methode ausgeführte Konvertierung ist vom Wert der <xref:System.DateTime.Kind%2A>\-Eigenschaft des `dateTime`\-Parameters abhängig, wie in der folgenden Tabelle dargestellt.  
  
|DateTime.Kind\-Eigenschaft|Conversion|  
|--------------------------------|----------------|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Konvertiert Ortszeit in UTC.|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Nimmt an, dass der `dateTime`\-Parameter Ortszeit darstellt, und konvertiert Ortszeit in UTC.|  
|<xref:System.DateTimeKind?displayProperty=fullName>|Gibt den `dateTime`\-Parameter unverändert zurück.|  
  
 Im folgenden Code wird die aktuelle Ortszeit in UTC konvertiert, und das Ergebnis wird auf der Konsole angezeigt.  
  
 [!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
 [!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]  
  
> [!NOTE]
>  Die <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName>\-Methode erzeugt notwendigerweise keine Ergebnisse, die mit der <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=fullName>\-Methode und <xref:System.DateTime.ToUniversalTime%2A?displayProperty=fullName>\-Methode identisch sind.  Wenn für die lokale Zeitzone des Hostsystems mehrere Anpassungsregeln gelten, wendet <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=fullName> die entsprechende Regel auf ein bestimmtes Datum und eine bestimmte Uhrzeit an.  Die anderen beiden Methoden wenden immer die letzte Anpassungsregel an.  
  
 Wenn der Datums\- und Uhrzeitwert weder die Ortszeit noch UTC darstellt, gibt die <xref:System.DateTime.ToUniversalTime%2A>\-Methode wahrscheinlich ein falsches Ergebnis zurück.  Mit der <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=fullName>\-Methode können Sie jedoch das Datum und die Uhrzeit aus einer bestimmten Zeitzone konvertieren. \(Ausführliche Informationen zum Abrufen eines <xref:System.TimeZoneInfo>\-Objekts, das die Zielzeitzone darstellt, finden Sie unter [Suchen der auf einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).\) Im folgenden Code wird die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=fullName>\-Methode verwendet, um Eastern Normalzeit in UTC zu konvertieren.  
  
 [!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
 [!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]  
  
 Beachten Sie, dass die Methode eine <xref:System.ArgumentException> auslöst, wenn die <xref:System.DateTime.Kind%2A>\-Eigenschaft des <xref:System.DateTime>\-Objekts und die Zeitzone nicht übereinstimmen.  Eine fehlende Übereinstimmung tritt dann auf, wenn die <xref:System.DateTime.Kind%2A>\-Eigenschaft <xref:System.DateTimeKind?displayProperty=fullName> ist, das <xref:System.TimeZoneInfo>\-Objekt jedoch nicht die lokale Zeitzone darstellt, oder wenn die <xref:System.DateTime.Kind%2A>\-Eigenschaft <xref:System.DateTimeKind?displayProperty=fullName> ist, das <xref:System.TimeZoneInfo>\-Objekt jedoch nicht <xref:System.DateTimeKind?displayProperty=fullName> entspricht.  
  
 Alle diese Methoden verwenden <xref:System.DateTime>\-Werte als Parameter und geben einen <xref:System.DateTime>\-Wert zurück.  Für <xref:System.DateTimeOffset>\-Werte verfügt die <xref:System.DateTimeOffset>\-Struktur über eine <xref:System.DateTimeOffset.ToUniversalTime%2A>\-Instanzmethode, mit der Datum und Uhrzeit der aktuellen Instanz in UTC konvertiert werden.  Im folgenden Beispiel werden mithilfe der <xref:System.DateTimeOffset.ToUniversalTime%2A>\-Methode die Ortszeit und mehrere andere Uhrzeiten in koordinierte Weltzeit \(UTC\) konvertiert.  
  
 [!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
 [!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]  
  
## Konvertieren von UTC in eine festgelegte Zeitzone  
 Weitere Informationen zum Konvertieren von UTC in Ortszeit finden Sie im folgenden Abschnitt, "Konvertieren von UTC in Ortszeit".  Um UTC in eine Uhrzeit einer beliebigen festgelegten Zeitzone zu konvertieren, rufen Sie die <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>\-Methode auf.  Diese Methode verwendet zwei Parameter:  
  
-   Die zu konvertierende UTC.  Hierbei muss es sich um einen <xref:System.DateTime>\-Wert handeln, dessen <xref:System.DateTime.Kind%2A>\-Eigenschaft auf <xref:System.DateTimeKind?displayProperty=fullName> oder <xref:System.DateTimeKind?displayProperty=fullName> festgelegt ist.  
  
-   Die Zeitzone, in die UTC konvertiert werden soll.  
  
 Im folgenden Code wird UTC in Central Normalzeit konvertiert.  
  
 [!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
 [!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]  
  
## Konvertieren von UTC in Ortszeit  
 Rufen Sie zum Konvertieren von UTC in Ortszeit die <xref:System.DateTime.ToLocalTime%2A>\-Methode des <xref:System.DateTime>\-Objekts auf, dessen Uhrzeit Sie konvertieren möchten.  Das genaue Verhalten der Methode ist vom Wert der <xref:System.DateTime.Kind%2A>\-Eigenschaft des Objekts abhängig, wie in der folgenden Tabelle dargestellt.  
  
|`DateTime.Kind`\-Eigenschaft|Conversion|  
|----------------------------------|----------------|  
|`DateTimeKind.Local`|Gibt den <xref:System.DateTime>\-Wert unverändert zurück.|  
|`DateTimeKind.Unspecified`|Nimmt an, dass der <xref:System.DateTime>\-Wert UTC ist, und konvertiert UTC in Ortszeit.|  
|`DateTimeKind.Utc`|Konvertiert den <xref:System.DateTime>\-Wert in Ortszeit.|  
  
 **Hinweis** Das Verhalten der <xref:System.TimeZone.ToLocalTime%2A?displayProperty=fullName>\-Methode ist mit dem der `DateTime.ToLocalTime`\-Methode identisch.  Sie verwendet einen einzelnen Parameter, wobei es sich um den zu konvertierenden Datums\- und Uhrzeitwert handelt.  
  
 Sie können die Uhrzeit auch in die Ortszeit einer beliebigen festgelegten Zeitzone konvertieren, indem Sie die `static` \(`Shared` in Visual Basic\) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=fullName>\-Methode verwenden.  Diese Vorgehensweise wird im nächsten Abschnitt erläutert.  
  
## Konvertieren zwischen zwei beliebigen Zeitzonen  
 Sie können Uhrzeiten zwischen zwei beliebigen Zeitzonen konvertieren, indem Sie eine der beiden folgenden `static`\-Methoden \(`Shared` in Visual Basic\) der <xref:System.TimeZoneInfo>\-Klasse verwenden:  
  
-   <xref:System.TimeZoneInfo.ConvertTime%2A>  
  
     Die Parameter dieser Methode sind das Datum und die Uhrzeit, die konvertiert werden sollen, ein `TimeZoneInfo`\-Objekt, das die Zeitzone des Datums\- und Uhrzeitwerts darstellt, sowie ein `TimeZoneInfo`\-Objekt, das die Zeitzone darstellt, in die der Datums\- und Uhrzeitwert konvertiert werden soll.  
  
-   <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>  
  
     Die Parameter dieser Methode sind das Datum und die Uhrzeit, die konvertiert werden sollen, ein Zeitzonenbezeichner des Datums\- und Uhrzeitwerts sowie ein Bezeichner der Zeitzone, in die der Datums\- und Uhrzeitwert konvertiert werden soll.  
  
 Für beide Methoden ist erforderlich, dass die <xref:System.DateTime.Kind%2A>\-Eigenschaft des zu konvertierenden Datums\- und Uhrzeitwerts und das <xref:System.TimeZoneInfo>\-Objekt oder der Zeitzonenbezeichner, der seine Zeitzone darstellt, einander entsprechen.  Andernfalls wird eine <xref:System.ArgumentException> ausgelöst.  Wenn zum Beispiel die `Kind`\-Eigenschaft des Datums\- und Uhrzeitwerts `DateTimeKind.Local` lautet, wird eine Ausnahme ausgelöst, wenn das als Parameter an die Methode übergebene `TimeZoneInfo`\-Objekt nicht gleich `TimeZoneInfo.Local` ist.  Es wird auch dann eine Ausnahme ausgelöst, wenn der als Parameter an die Methode übergebene Bezeichner nicht gleich `TimeZoneInfo.Local.Id` ist.  
  
 Im folgenden Beispiel wird die <xref:System.TimeZoneInfo.ConvertTime%2A>\-Methode zum Konvertieren von Hawaii Normalzeit in Ortszeit verwendet.  
  
 [!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
 [!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]  
  
## Konvertieren von DateTimeOffset\-Werten  
 Datums\- und Uhrzeitwerte, die durch <xref:System.DateTimeOffset>\-Objekte dargestellt werden, unterstützen Zeitzonen nicht vollständig, da das Objekt zum Zeitpunkt der Instanziierung nicht mit der Zeitzone verknüpft wird.  In vielen Fällen muss die Anwendung einfach nur ein Datum und eine Uhrzeit basierend auf zwei verschiedenen Offsets von UTC konvertieren, statt basierend auf der Uhrzeit in bestimmten Zeitzonen.  Um diese Konvertierung auszuführen, können Sie die <xref:System.DateTimeOffset.ToOffset%2A>\-Methode der aktuellen Instanz aufrufen.  Der einzige Parameter dieser Methode ist der Offset des neuen Datums\- und Uhrzeitwerts, den die Methode zurückgeben soll.  
  
 Wenn zum Beispiel das Datum und die Uhrzeit einer Benutzeranforderung für eine Webseite bekannt und als Zeichenfolge im Format MM\/tt\/jjjj hh:mm:ss zzzz serialisiert sind, konvertiert die folgende `ReturnTimeOnServer`\-Methode diesen Datums\- und Uhrzeitwert in Datum und Uhrzeit auf dem Webserver.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)]  
  
 Wenn die Zeichenfolge "9\/1\/2007 5:32 übergeben wird: 07 \-05:00", das Datum und die Uhrzeit in einer Zeitzone fünf Stunden vor UTC darstellt, gibt die Methode " 9\/1\/2007 3:32: 07 Morgens\-\-07:00 für einen Server in der Zeitzone Pacific Normalzeit.  
  
 Die <xref:System.TimeZoneInfo>\-Klasse umfasst auch eine Überladung der <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName>\-Methode, mit der Zeitzonenkonvertierungen anhand von <xref:System.DateTimeOffset>\-Werten durchgeführt werden.  Die Parameter der Methode sind ein <xref:System.DateTimeOffset>\-Wert und ein Verweis auf die Zeitzone, in die die Uhrzeit konvertiert werden soll.  Der Methodenaufruf gibt einen <xref:System.DateTimeOffset>\-Wert zurück.  Die `ReturnTimeOnServer`\-Methode im vorhergehenden Beispiel kann beispielsweise so umgeschrieben werden, dass die <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>\-Methode aufgerufen wird.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]  
  
## Siehe auch  
 <xref:System.TimeZoneInfo>   
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Suchen der auf einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)