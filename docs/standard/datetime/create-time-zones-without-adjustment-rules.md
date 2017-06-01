---
title: "Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln | Microsoft Docs"
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
  - "Zeitzonen [.NET Framework], Anpassungsregel"
  - "Zeitzonen [.NET Framework], Erstellen"
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Erstellen von Zeitzonen ohne Anpassungsregeln
Die genauen Zeitzonendaten, die eine Anwendung benötigt, können aus mehreren Gründen auf einem bestimmten System nicht vorhanden sein:  
  
-   Die Zeitzone wurde zuvor noch nicht in der Registrierung des lokalen Systems definiert.  
  
-   Daten der Zeitzone wurden geändert oder aus der Registrierung entfernt.  
  
-   Die Zeitzone ist vorhanden, weist jedoch keine genauen Informationen über Zeitzonenanpassungen für einen bestimmten historischen Zeitraum auf.  
  
 In diesen Fällen können Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode aufrufen, um die von der Anwendung benötigte Zeitzone zu definieren.  Sie können die Überladungen dieser Methode zum Erstellen einer Zeitzone mit oder ohne Anpassungsregeln verwenden.  Wenn die Zeitzone die Sommerzeit unterstützt, können Sie Anpassungen mit festen oder beweglichen Anpassungsregeln definieren. \(Definitionen dieser Begriffe finden Sie im Abschnitt "Zeitzonenterminologie" unter [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md).\)  
  
> [!IMPORTANT]
>  Benutzerdefinierte Zeitzonen, die durch Aufrufen der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode erstellt werden, werden nicht zur Registrierung hinzugefügt.  Stattdessen kann nur über den Objektverweis, der vom Aufruf der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\-Methode zurückgegeben wird, darauf zugegriffen werden.  
  
 In diesem Thema wird erläutert, wie Sie eine Zeitzone ohne Anpassungsregeln erstellen.  Informationen zum Erstellen einer Zeitzone, die Anpassungsregeln für die Sommerzeit unterstützt, finden Sie unter [Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).  
  
### So erstellen Sie eine Zeitzone ohne Anpassungsregeln  
  
1.  Definieren Sie den Anzeigenamen der Zeitzone.  
  
     Der Anzeigename folgt einem gewissen Standardformat. Hierbei wird der Offset der Zeitzone von der koordinierten Weltzeit \(Coordinated Universal Time, UTC\) in Klammern eingeschlossen, gefolgt von einer Zeichenfolge, die die Zeitzone, einen oder mehrere Orte in der Zeitzone oder ein oder mehrere Länder oder Regionen in der Zeitzone identifiziert.  
  
2.  Definieren Sie den Namen der Normalzeit der Zeitzone.  Diese Zeichenfolge wird normalerweise auch als der Bezeichner der Zeitzone verwendet.  
  
3.  Wenn Sie einen anderen Bezeichner als den Standardnamen der Zeitzone verwenden möchten, definieren Sie den Zeitzonenbezeichner.  
  
4.  Instanziieren Sie ein <xref:System.TimeSpan>\-Objekt, das den Offset der Zeitzone von UTC definiert.  Zeitzonen mit Uhrzeiten, die nach UTC liegen, weisen einen positiven Offset auf.  Zeitzonen mit Uhrzeiten, die vor UTC liegen, weisen einen negativen Offset auf.  
  
5.  Rufen Sie die <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=fullName>\-Methode auf, um die neue Zeitzone zu instanziieren.  
  
## Beispiel  
 Im folgenden Beispiel wird eine benutzerdefinierte Zeitzone für Mawson, Antarktis, definiert, die keine Anpassungsregeln verwendet.  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
 [!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]  
  
 Die Zeichenfolge, die der <xref:System.TimeZoneInfo.DisplayName%2A>\-Eigenschaft zugewiesen ist, weist ein standardmäßiges Format auf, bei dem auf den Offset der Zeitzone von UTC eine benutzerfreundliche Beschreibung der Zeitzone folgt.  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Dem Projekt muss ein Verweis auf System.Core.dll hinzugefügt werden.  
  
-   Die folgenden Namespaces müssen importiert werden:  
  
     [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
     [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]  
  
## Siehe auch  
 [Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)   
 [Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)   
 [Gewusst wie: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)