---
title: "Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen | Microsoft Docs"
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
  - "Datumsangaben [.NET Framework], Addieren und Subtrahieren"
  - "Zeitzonen [.NET Framework], Arithmetische Operationen"
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Verwenden von Zeitzonen in arithmetischen Datums- und Uhrzeitoperationen
Normalerweise werden beim Durchführen von arithmetischen Datums\- und Uhrzeitoperationen mit <xref:System.DateTime>\-Werten oder <xref:System.DateTimeOffset>\-Werten in den Ergebnissen keine Zeitzonenanpassungsregeln berücksichtigt.  Dies trifft auch zu, wenn die Zeitzone des Datums\- und Uhrzeitwerts eindeutig erkennbar ist \(wenn die <xref:System.DateTime.Kind%2A>\-Eigenschaft zum Beispiel auf <xref:System.DateTimeKind> festgelegt ist\).  In diesem Thema wird erläutert, wie Sie arithmetische Operationen für Datums\- und Uhrzeitwerte durchführen, die zu einer bestimmten Zeitzone gehören.  Die Ergebnisse der arithmetischen Operationen berücksichtigen die Anpassungsregeln der Zeitzone.  
  
### So wenden Sie Anpassungsregeln auf arithmetische Datums\- und Uhrzeitoperationen an  
  
1.  Implementieren Sie eine beliebige Methode, mit der ein Datums\- und Uhrzeitwert eng mit der Zeitzone verknüpft wird, zu der er gehört.  Deklarieren Sie z. B. eine Struktur, die sowohl den Datums\- als auch den Uhrzeitwert und seine Zeitzone einschließt.  Im folgenden Beispiel wird dieser Ansatz verwendet, um einen <xref:System.DateTime>\-Wert mit seiner Zeitzone zu verknüpfen.  
  
     [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
     [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]  
  
2.  Konvertieren Sie eine koordinierte Weltzeit \(Coordinated Universal Time, UTC\), indem Sie entweder die <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>\-Methode oder die <xref:System.TimeZoneInfo.ConvertTime%2A>\-Methode aufrufen.  
  
3.  Führen Sie die arithmetische Operation für die UTC\-Zeit aus.  
  
4.  Konvertieren Sie die Zeit von UTC in die mit der ursprünglichen Zeit verknüpfte Zeitzone, indem Sie die <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=fullName>\-Methode aufrufen.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Stunden und dreißig Minuten hinzugefügt am 9. März 2008 um 1:30 Uhr Central Normalzeit.  Die Umstellung auf Sommerzeit erfolgt in der Zeitzone dreißig Minuten später, um 2:00 Uhr am 9. März 2008 auf.  Da in diesem Beispiel die vier Schritten, die im vorherigen Abschnitt aufgeführten, ist das Ergebnis die richtige Zeit von 5:00 Uhr am 9. März 2008.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
 [!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]  
  
 Sowohl für den <xref:System.DateTime>\-Wert als auch den <xref:System.DateTimeOffset>\-Wert wird die Zuordnung zu einer Zeitzone, der sie möglicherweise angehören, aufgehoben.  Um arithmetische Datums\- und Uhrzeitoperationen so durchführen zu können, dass Anpassungsregeln für Zeitzonen automatisch angewendet werden, muss die Zeitzone, zu der der Datums\- und Uhrzeitwert gehört, direkt identifizierbar sein.  Dies bedeutet, dass Datum und Uhrzeit sowie die zugeordnete Zeitzone eng verknüpft sein müssen.  Hierzu gibt es mehrere Möglichkeiten, einschließlich die folgenden:  
  
-   Nehmen Sie an, dass alle in einer Anwendung verwendeten Uhrzeiten zu einer bestimmten Zeitzone gehören.  Obwohl dieser Ansatz in einigen Fällen geeignet ist, bietet er jedoch nur eingeschränkte Flexibilität sowie möglicherweise eine eingeschränkte Portabilität.  
  
-   Definieren Sie einen Typ, der ein Datum und eine Uhrzeit eng mit der zugehörigen Zeitzone verknüpft, indem Sie beide als Felder des Typs einschließen.  Dieser Ansatz wird im Codebeispiel verwendet, in dem eine Struktur zum Speichern des Datums und der Uhrzeit sowie der Zeitzone in zwei Memberfeldern definiert wird.  
  
 Das Beispiel veranschaulicht, wie arithmetische Operationen mit <xref:System.DateTime>\-Werten durchgeführt werden, sodass Anpassungsregeln für Zeitzonen auf das Ergebnis angewendet werden.  <xref:System.DateTimeOffset>\-Werte können jedoch genauso einfach verwendet werden.  Das folgende Beispiel veranschaulicht, wie der Code des ursprünglichen Beispiels so angepasst werden kann, dass <xref:System.DateTimeOffset>\-Werte statt <xref:System.DateTime>\-Werten verwendet werden.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]  
  
 Beachten Sie hierbei Folgendes: Wenn die Addition für den <xref:System.DateTimeOffset>\-Wert einfach durchgeführt wird, ohne dass er zunächst in UTC konvertiert wurde, gibt das Ergebnis den richtigen Zeitpunkt wieder, wobei der Offset jedoch nicht den richtigen Zeitpunkt der für diese Uhrzeit zugewiesenen Zeitzone widerspiegelt.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Dem Projekt muss ein Verweis auf System.Core.dll hinzugefügt werden.  
  
-   Der <xref:System>\-Namespace muss mit der `using`\-Anweisung \(in C\#\-Code erforderlich\) importiert werden.  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Durchführen arithmetischer Datums\- und Uhrzeitoperationen](../../../docs/standard/datetime/performing-arithmetic-operations.md)