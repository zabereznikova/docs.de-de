---
title: "Durchf&#252;hren arithmetischer Datums- und Uhrzeitoperationen | Microsoft Docs"
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
  - "Arithmetische Operationen [.NET Framework], Datum und Uhrzeit"
  - "Datumsangaben [.NET Framework], Arithmetische Operationen"
  - "Datumsangaben [.NET Framework], Vergleichen"
  - "DateTime-Struktur, Arithmetische Operationen"
  - "DateTimeOffset-Struktur, Arithmetische Operationen"
  - "Zeitzonen [.NET Framework], Arithmetische Operationen"
  - "Zeiten [.NET Framework], Arithmetische Operationen"
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Durchf&#252;hren arithmetischer Datums- und Uhrzeitoperationen
Die <xref:System.DateTime>\-Struktur und die <xref:System.DateTimeOffset>\-Struktur stellen zwar beide Member bereit, die arithmetische Operationen für ihre Werte durchführen, die Ergebnisse dieser arithmetischen Operationen fallen jedoch sehr unterschiedlich aus.  In diesem Thema werden diese Unterschiede untersucht, mit der jeweiligen Zeitzonenunterstützung für Datums\- und Uhrzeitdaten in Beziehung gesetzt und Informationen zur Durchführung von Operationen mit vollständiger Zeitzonenunterstützung für Datums\- und Uhrzeitdaten bereitgestellt.  
  
## Vergleiche und arithmetische Operationen mit "DateTime"\-Werten  
 Ab .NET Framework, Version 2.0, bieten <xref:System.DateTime>\-Werte eine eingeschränkte Unterstützung von Zeitzonen.  Mit der <xref:System.DateTime.Kind%2A?displayProperty=fullName>\-Eigenschaft kann ein <xref:System.DateTimeKind>\-Wert einem Datum und einer Uhrzeit zugewiesen werden, um anzugeben, ob es sich um die lokale Zeit, die koordinierte Weltzeit \(UTC\) oder die Zeit in einer nicht angegebenen Zeitzone handelt.  Diese eingeschränkten Zeitzoneninformationen werden jedoch ignoriert, wenn <xref:System.DateTime>\-Werte verglichen oder arithmetische Datums\- und Uhrzeitoperationen für sie durchgeführt werden.  Im folgenden Beispiel, in dem die aktuelle lokale Zeit mit der aktuellen UTC\-Zeit verglichen wird, wird dies veranschaulicht.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]  
  
 Die <xref:System.DateTime.CompareTo%28System.DateTime%29>\-Methode gemeldet, dass die lokale Zeit früher als die UTC\-Zeit ist, und die Subtraktion gibt an, dass die Differenz zwischen der UTC\-Zeit und der lokalen Zeit für ein System in der Zeitzone Pacific Normalzeit sieben Stunden beträgt.  Da diese beiden Werte jedoch unterschiedliche Darstellungen eines bestimmten Zeitpunkts liefern, ist in diesem Fall klar, dass das Zeitintervall vollständig dem Offset der lokalen Zeitzone von der UTC\-Zeit zuzuordnen ist.  
  
 Verallgemeinert bedeutet dies, dass sich die <xref:System.DateTime.Kind%2A?displayProperty=fullName>\-Eigenschaft nicht auf die von <xref:System.DateTime>\-Methoden für Vergleiche und arithmetische Operationen zurückgegebenen Ergebnisse auswirkt \(wie der Vergleich zweier identischer Zeitpunkte zeigt\), aber die Interpretation dieser Ergebnisse beeinflussen kann.  Beispiel:  
  
-   Das Ergebnis einer beliebigen arithmetischen Operation für zwei Datums\- und Uhrzeitwerte, deren <xref:System.DateTime.Kind%2A?displayProperty=fullName>\-Eigenschaft jeweils <xref:System.DateTimeKind> entspricht, gibt das tatsächliche Zeitintervall zwischen den beiden Werten wieder.  Der Vergleich zweier solcher Datums\- und Uhrzeitwerte gibt entsprechend die Beziehung zwischen den Zeiten genau wieder.  
  
-   Das Ergebnis einer arithmetischen oder Vergleichsoperation für zwei Datums\- und Uhrzeitwerte, deren <xref:System.DateTime.Kind%2A?displayProperty=fullName>\-Eigenschaft jeweils <xref:System.DateTimeKind> entspricht, oder für zwei Datums\- und Uhrzeitwerte mit verschiedenen <xref:System.DateTime.Kind%2A?displayProperty=fullName>\-Eigenschaftswerten gibt den Zeitunterschied zwischen den beiden Werten wieder.  
  
-   Bei arithmetischen oder Vergleichsoperationen für lokale Datums\- und Uhrzeitwerte wird nicht berücksichtigt, ob ein bestimmter Wert mehrdeutig oder ungültig ist. Zudem werden die Auswirkungen von Anpassungsregeln ignoriert, die aus dem Übergang der lokalen Zeitzone von oder zur Sommerzeit resultieren.  
  
-   Das Ergebnis einer Operation, mit der der Unterschied zwischen der UTC\-Zeit und der lokalen Zeit verglichen oder berechnet wird, beinhaltet ein Zeitintervall, das dem Offset der lokalen Zeitzone von der koordinierten Weltzeit entspricht.  
  
-   Jede Operation, mit der der Unterschied zwischen einer nicht spezifizierten Zeit und der UTC\-Zeit oder der lokalen Zeit verglichen oder berechnet wird, gibt die einfache Uhrzeit wieder.  Zeitzonenunterschiede und entsprechende Anpassungsregeln werden ignoriert und im Ergebnis nicht wiedergegeben.  
  
-   Jede Operation, mit der der Unterschied zwischen zwei nicht spezifizierten Zeiten verglichen oder berechnet wird, kann ein unbekanntes Intervall beinhalten, das den Unterschied zwischen der Zeit in zwei verschiedenen Zeitzonen wiedergibt.  
  
 Es gibt viele Szenarios, in denen sich Zeitzonenunterschiede nicht auf Datums\- und Uhrzeitberechnungen auswirken \(einige Beispiele finden Sie unter [Auswählen zwischen "DateTime", "DateTimeOffset", "TimeSpan" und "TimeZoneInfo"](../../../docs/standard/datetime/choosing-between-datetime.md)\) oder in denen der Kontext von Datums\- und Uhrzeitdaten die Bedeutung von Vergleichen oder arithmetischen Operationen definiert.  
  
## Vergleiche und arithmetische Operationen mit "DateTimeOffset"\-Werten  
 Ein <xref:System.DateTimeOffset>\-Wert enthält nicht nur ein Datum und eine Uhrzeit, sondern auch einen Offset, der das Datum und die Uhrzeit bezogen auf die koordinierte Weltzeit eindeutig definiert.  Dadurch ist es möglich, eine etwas andere Definition von Gleichheit als für <xref:System.DateTime>\-Werte zu verwenden.  Während <xref:System.DateTime>\-Werte gleich sind, wenn sie den gleichen Datums\- und Uhrzeitwert aufweisen, sind <xref:System.DateTimeOffset>\-Werte gleich, wenn sie sich beide auf den gleichen Zeitpunkt beziehen.  Ein <xref:System.DateTimeOffset>\-Wert ist somit genauer und erfordert in Vergleichen und den meisten arithmetischen Operationen, mit denen das Intervall zwischen Datums\- und Uhrzeitwerten bestimmt wird, einen geringeren Interpretationsaufwand.  Dieser Verhaltensunterschied wird im folgenden Beispiel veranschaulicht, das dem <xref:System.DateTimeOffset>\-Äquivalent zum vorherigen Beispiel entspricht, in dem <xref:System.DateTime>\-Werte für die lokale Zeit und die UTC\-Zeit verglichen wurden.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]  
  
 In diesem Beispiel gibt die <xref:System.DateTimeOffset.CompareTo%2A>\-Methode an, dass die aktuelle lokale Zeit und die aktuelle UTC\-Zeit identisch sind, und die Subtraktion von <xref:System.DateTimeOffset>\-Werten ergibt, dass der Unterschied zwischen den beiden Zeiten <xref:System.TimeSpan.Zero?displayProperty=fullName> ist.  
  
 Die größte Einschränkung bei der Verwendung von <xref:System.DateTimeOffset>\-Werten in arithmetischen Datums\- und Uhrzeitoperationen besteht darin, dass <xref:System.DateTimeOffset>\-Werte keine vollständige Zeitzonenunterstützung bieten.  Wenn einer <xref:System.DateTimeOffset>\-Variablen ein Wert zugeordnet wird, gibt dieser <xref:System.DateTimeOffset>\-Wert zunächst zwar den Offset einer Zeitzone von der koordinierten Weltzeit wieder, seine Zuordnung zur Zeitzone wird anschließend jedoch aufgehoben.  Da er keiner identifizierbaren Zeit mehr direkt zugeordnet ist, werden bei der Addition und Subtraktion von Datums\- und Uhrzeitintervallen die Anpassungsregeln einer Zeitzone nicht berücksichtigt.  
  
 Um zu veranschaulichen, wird der Übergang zur Sommerzeit in der Zeitzone Central Normalzeit um 2:00 Uhr am 9. März 2008 auf.  Das bedeutet, dass zwei hinzufügen und sich ein Intervall auf eine zentrale Normalzeit von 1:30 Uhr am 9. März 2008, sollte ein Datum und eine Zeit von 5:00 Uhr am 9. März 2008 erzeugen.  Da das folgende Beispiel zeigt, ist das Ergebnis der Addition 4:00 Uhr am 9. März 2008.  Beachten Sie, dass das Ergebnis dieser Operation den richtigen Zeitpunkt wiedergibt, auch wenn es nicht die Zeit in der Zeitzone ist, die uns interessiert \(d. h. es entspricht nicht dem erwarteten Zeitzonenoffset\).  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]  
  
## Arithmetische Operationen mit Zeiten in Zeitzonen  
 Die <xref:System.TimeZoneInfo>\-Klasse beinhaltet eine Reihe von Konvertierungsmethoden, die automatisch Anpassungen anwenden, wenn sie die Zeiten einer Zeitzone in die einer anderen konvertieren.  Hierzu gehört Folgendes:  
  
-   Die <xref:System.TimeZoneInfo.ConvertTime%2A>\-Methode und die <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>\-Methode, die Zeiten zwischen zwei beliebigen Zeitzonen konvertieren.  
  
-   Die <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>\-Methode und die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>\-Methode, die die Zeit in einer bestimmten Zeitzone in die koordinierte Weltzeit konvertieren oder umgekehrt.  
  
 Ausführliche Informationen finden Sie unter [Konvertieren von Uhrzeiten zwischen Zeitzonen](../../../docs/standard/datetime/converting-between-time-zones.md).  
  
 Die <xref:System.TimeZoneInfo>\-Klasse stellt keine Methoden bereit, die beim Durchführen von arithmetischen Datums\- und Uhrzeitoperationen automatisch Anpassungsregeln anwenden.  Dies ist jedoch möglich, indem Sie die Zeit in einer Zeitzone in die koordinierte Weltzeit konvertieren, die arithmetische Operation durchführen und anschließend die koordinierte Weltzeit wieder in die Zeit in der Zeitzone konvertieren.  Ausführliche Informationen finden Sie unter [Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums\- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).  
  
 Beispielsweise ist der folgende Code dem vorherigen Code ähnlich, wie der zu 2:00 Uhr am 9. März 2008 hinzufügen.  Da er jedoch eine Zeit in der Zeitzone Central Normalzeit in die koordinierte Weltzeit konvertiert, bevor er arithmetische Datums\- und Uhrzeitoperationen durchführt, und danach das Ergebnis von der koordinierten Weltzeit wieder in die Central Normalzeit konvertiert, gibt die Zeit den Übergang der Zeitzone Central Normalzeit zur Sommerzeit wieder.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums\- und Uhrzeitoperationen](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)