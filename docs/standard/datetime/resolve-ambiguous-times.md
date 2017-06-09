---
title: "Gewusst wie: Aufl&#246;sen von mehrdeutigen Zeiten | Microsoft Docs"
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
  - "Mehrdeutige Zeit [.NET Framework]"
  - "Zeitzonen [.NET Framework], Mehrdeutige Zeit"
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Aufl&#246;sen von mehrdeutigen Zeiten
Bei einer mehrdeutigen Zeit handelt es sich um eine Zeit, die mehreren koordinierten Weltzeiten \(Coordinated Universal Time; UTC\) zugeordnet ist.  Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise bei der Umstellung von der Sommerzeit in einer Zeitzone auf die Standardzeit.  Bei der Behandlung einer mehrdeutigen Zeit können Sie wie folgt vorgehen:  
  
-   Treffen Sie eine Annahme darüber, wie die Zeit UTC zugeordnet ist.  Sie können zum Beispiel annehmen, dass eine mehrdeutige Zeit immer als Standardzeit der Zeitzone ausgedrückt wird.  
  
-   Wenn die mehrdeutige Zeit vom Benutzer eingegeben wurde, können Sie dem Benutzer die Auslösung der Mehrdeutigkeit überlassen.  
  
 In diesem Thema wird erläutert, wie eine mehrdeutige Zeit durch die Annahme aufgelöst wird, dass sie die Standardzeit der Zeitzone darstellt.  
  
### So ordnen Sie eine mehrdeutige Zeit der Standardzeit einer Zeitzone zu  
  
1.  Rufen Sie die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A>\-Methode auf, um festzustellen, ob die Zeit mehrdeutig ist.  
  
2.  Wenn die Zeit mehrdeutig ist, subtrahieren Sie die Zeit vom <xref:System.TimeSpan>\-Objekt, das von der <xref:System.TimeZoneInfo.BaseUtcOffset%2A>\-Eigenschaft der Zeitzone zurückgegeben wird.  
  
3.  Rufen Sie die `static` \(`Shared` in Visual Basic .NET\) <xref:System.DateTime.SpecifyKind%2A>\-Methode auf, um für die <xref:System.DateTime.Kind%2A>\-Eigenschaft des UTC\-Datums und der UTC\-Uhrzeit den Wert <xref:System.DateTimeKind?displayProperty=fullName> festzulegen.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie eine mehrdeutige Zeit in UTC konvertieren, indem davon ausgegangen wird, dass sie die Standardzeit der lokalen Zeitzone darstellt.  
  
 [!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
 [!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]  
  
 Das Beispiel umfasst die `ResolveAmbiguousTime`\-Methode, mit der ermittelt wird, ob der an sie übergebene <xref:System.DateTime>\-Wert mehrdeutig ist.  Wenn der Wert mehrdeutig ist, gibt die Methode einen <xref:System.DateTime>\-Wert zurück, der die entsprechende UTC\-Zeit darstellt.  Die Methode führt diese Konvertierung durch, indem der Wert der <xref:System.TimeZoneInfo.BaseUtcOffset%2A>\-Eigenschaft der lokalen Zeitzone von der Ortszeit subtrahiert wird.  
  
 Normalerweise wird eine mehrdeutige Zeit behandelt, indem die <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>\-Methode aufgerufen wird, um ein Array von <xref:System.TimeSpan>\-Objekten, die die möglichen UTC\-Offsets für die mehrdeutige Zeit enthalten, abzurufen.  In diesem Beispiel wird jedoch die willkürliche Annahme getroffen, dass eine mehrdeutige Zeit immer der Standardzeit der Zeitzone zugeordnet ist.  Die <xref:System.TimeZoneInfo.BaseUtcOffset%2A>\-Eigenschaft gibt den Offset zwischen UTC und der Standardzeit einer Zeitzone zurück.  
  
 In diesem Beispiel erfolgen alle Verweise auf die lokale Zeitzone über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>\-Eigenschaft, und die lokale Zeitzone ist nie einer Objektvariablen zugewiesen.  Hierbei handelt es sich um eine empfohlene Vorgehensweise, da durch einen Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName>\-Methode alle Objekte, denen die lokale Zeitzone zugewiesen ist, ungültig werden.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Dem Projekt muss ein Verweis auf System.Core.dll hinzugefügt werden.  
  
-   Der <xref:System>\-Namespace muss mit der `using`\-Anweisung \(in C\#\-Code erforderlich\) importiert werden.  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Gewusst wie: Auflösen mehrdeutiger Zeiten durch den Benutzer](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)