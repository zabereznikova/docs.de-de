---
title: "Gewusst wie: Aufl&#246;sen mehrdeutiger Zeiten durch den Benutzer | Microsoft Docs"
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
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Aufl&#246;sen mehrdeutiger Zeiten durch den Benutzer
Bei einer mehrdeutigen Zeit handelt es sich um eine Zeit, die mehreren koordinierten Weltzeiten \(Coordinated Universal Time; UTC\) zugeordnet ist.  Sie tritt auf, wenn die Uhrzeit zurückgestellt wird, beispielsweise bei der Umstellung von der Sommerzeit in einer Zeitzone auf die Standardzeit.  Bei der Behandlung einer mehrdeutigen Zeit können Sie wie folgt vorgehen:  
  
-   Wenn die mehrdeutige Zeit vom Benutzer eingegeben wurde, können Sie dem Benutzer die Auslösung der Mehrdeutigkeit überlassen.  
  
-   Treffen Sie eine Annahme darüber, wie die Zeit UTC zugeordnet ist.  Sie können zum Beispiel annehmen, dass eine mehrdeutige Zeit immer als Standardzeit der Zeitzone ausgedrückt wird.  
  
 In diesem Thema wird erläutert, wie Sie einen Benutzer eine mehrdeutige Zeit auflösen lassen.  
  
### So lassen Sie einen Benutzer eine mehrdeutige Zeit auflösen  
  
1.  Lassen Sie das Datum und die Uhrzeit vom Benutzer eingeben.  
  
2.  Rufen Sie die <xref:System.TimeZoneInfo.IsAmbiguousTime%2A>\-Methode auf, um festzustellen, ob die Zeit mehrdeutig ist.  
  
3.  Wenn die Zeit mehrdeutig ist, rufen Sie die <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>\-Methode auf, um ein Array von <xref:System.TimeSpan>\-Objekten abzurufen.  Jedes Element im Array enthält einen UTC\-Offset, dem die mehrdeutige Zeit zugeordnet werden kann.  
  
4.  Lassen Sie den Benutzer den gewünschten Offset auswählen.  
  
5.  Ermitteln Sie das UTC\-Datum und die UTC\-Uhrzeit, indem Sie den vom Benutzer ausgewählten Offset von der Ortszeit abziehen.  
  
6.  Rufen Sie die `static` \(`Shared` in Visual Basic .NET\) <xref:System.DateTime.SpecifyKind%2A>\-Methode auf, um für die <xref:System.DateTime.Kind%2A>\-Eigenschaft des UTC\-Datums und der UTC\-Uhrzeit den Wert <xref:System.DateTimeKind?displayProperty=fullName> festzulegen.  
  
## Beispiel  
 Im folgenden Beispiel wird der Benutzer zur Eingabe eines Datums und einer Uhrzeit aufgefordert. Wenn diese nicht eindeutig sind, kann der Benutzer die UTC\-Zeit auswählen, die der mehrdeutigen Zeit zugeordnet ist.  
  
 [!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
 [!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]  
  
 Der Kern des Beispielcodes verwendet ein Array von <xref:System.TimeSpan>\-Objekten, um mögliche Offsets der mehrdeutigen Zeit von UTC anzugeben.  Die Bedeutung dieser Offsets ist für den Benutzer wahrscheinlich jedoch nicht ersichtlich.  Um die Bedeutung der Offsets klarzustellen, gibt der Code auch an, ob ein Offset die Normalzeit der lokalen Zeitzone darstellt oder die entsprechende Sommerzeit.  Der Code ermittelt, welche Zeit die Normalzeit und welche die Sommerzeit ist, indem der Offset mit dem Wert der <xref:System.TimeZoneInfo.BaseUtcOffset%2A>\-Eigenschaft verglichen wird.  Diese Eigenschaft gibt den Unterschied zwischen UTC und der Normalzeit der Zeitzone an.  
  
 In diesem Beispiel erfolgen alle Verweise auf die lokale Zeitzone über die <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>\-Eigenschaft, und die lokale Zeitzone ist nie einer Objektvariablen zugewiesen.  Hierbei handelt es sich um eine empfohlene Vorgehensweise, da durch einen Aufruf der <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName>\-Methode alle Objekte, denen die lokale Zeitzone zugewiesen ist, ungültig werden.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Dem Projekt muss ein Verweis auf System.Core.dll hinzugefügt werden.  
  
-   Der <xref:System>\-Namespace muss mit der `using`\-Anweisung \(in C\#\-Code erforderlich\) importiert werden.  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Gewusst wie: Auflösen von mehrdeutigen Zeiten](../../../docs/standard/datetime/resolve-ambiguous-times.md)