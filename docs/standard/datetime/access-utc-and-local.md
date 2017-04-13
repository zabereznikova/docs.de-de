---
title: "Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte | Microsoft Docs"
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
  - "Zugriff auf lokale Zeitzone"
  - "Vordefinierte Zeitzonen"
  - "Zeitzonen [.NET Framework], Lokal"
  - "Zeitzonen [.NET Framework], Abrufen"
  - "Zeitzonen [.NET Framework], UTC"
  - "UTC-Zeiten, Vordefiniert"
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte
Die <xref:System.TimeZoneInfo>\-Klasse verfügt über zwei Eigenschaften, <xref:System.TimeZoneInfo.Utc%2A> und <xref:System.TimeZoneInfo.Local%2A>, mit denen der Code auf vordefinierte Zeitzonenobjekte zugreifen kann.  In diesem Thema wird erläutert, wie auf die <xref:System.TimeZoneInfo>\-Objekte zugegriffen wird, die von diesen Eigenschaften zurückgegeben werden.  
  
### So greifen Sie auf das TimeZoneInfo\-Objekt der koordinierten Weltzeit \(Coordinated Universal Time, UTC\) zu  
  
1.  Verwenden Sie die `static` \(`Shared` in Visual Basic\) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName>\-Eigenschaft zum Zugreifen auf die koordinierte Weltzeit \(Coordinated Universal Time, UTC\).  
  
2.  Statt das von der Eigenschaft zurückgegebene <xref:System.TimeZoneInfo>\-Objekt einer Objektvariablen zuzuweisen, sollten Sie weiterhin über die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName>\-Eigenschaft auf die koordinierte Weltzeit \(UTC\) zugreifen.  
  
### So greifen Sie auf die lokale Zeitzone zu  
  
1.  Verwenden Sie die `static` \(`Shared` in Visual Basic\) <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>\-Eigenschaft zum Zugreifen auf die Zeitzone des lokalen Systems.  
  
2.  Statt das von der Eigenschaft zurückgegebene <xref:System.TimeZoneInfo>\-Objekt einer Objektvariablen zuzuweisen, sollten Sie weiterhin über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>\-Eigenschaft auf die lokale Zeitzone zugreifen.  
  
## Beispiel  
 Der folgende Code verwendet die <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>\-Eigenschaften <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName>, um einer Uhrzeit aus den USA und kanadisches von der Ost\-Normalzeit\-Zone zu konvertieren, sowie den Zeitzonennamen in der Konsole angezeigt werden.  
  
 [!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
 [!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]  
  
 Sie sollten immer über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>\-Eigenschaft auf die lokale Zeitzone zugreifen und nicht die lokale Zeitzone einer <xref:System.TimeZoneInfo>\-Objektvariablen zuweisen.  Sie sollten entsprechend auch immer über die <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName>\-Eigenschaft auf die koordinierte Weltzeit \(UTC\) zugreifen und nicht die UTC\-Zone einer <xref:System.TimeZoneInfo>\-Objektvariablen zuweisen.  Dies verhindert, dass die <xref:System.TimeZoneInfo>\-Objektvariable durch einen Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName>\-Methode ungültig wird.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Dem Projekt muss ein Verweis auf System.Core.dll hinzugefügt werden.  
  
-   Der <xref:System>\-Namespace muss mit der `using`\-Anweisung \(in C\#\-Code erforderlich\) importiert werden.  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Suchen der auf einem lokalen System definierten Zeitzonen](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)   
 [Gewusst wie: Instanziieren eines TimeZoneInfo\-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md)