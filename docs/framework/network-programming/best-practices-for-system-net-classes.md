---
title: "Bew&#228;hrte Methoden f&#252;r System.Net-Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Senden von Daten, Bewährte Methoden"
  - "Anfordern von Daten aus dem Internet, Bewährte Methoden"
  - "WebRequest-Klasse, Bewährte Methoden"
  - "Datenanforderungen, Bewährte Methoden"
  - "WebResponse-Klasse, Bewährte Methoden"
  - "Bewährte Methoden, Datenanforderungen"
  - "Empfangen von Daten, Bewährte Methoden"
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Bew&#228;hrte Methoden f&#252;r System.Net-Klassen
Die folgenden Empfehlungen helfen Ihnen, die Klassen verwenden, die in <xref:System.Net> zu den besten Vorteil enthalten sind:  
  
-   Verwenden Sie <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse>, wann immer möglich anstelle der Typumwandlung auf den Nachfolgerklassen.  Anwendungen, die **WebRequest** und **WebResponse** verwenden, können neue Internetprotokolle nutzen, ohne umfangreiche Codeänderungen zu erfordern.  
  
-   Wenn von ASP.NET\-Anwendungen schreibt, die auf einem Server mithilfe der **System.Net**\-Klassen ausgeführt werden, ist es häufig, einem Leistungsstandpunkt besser, die asynchronen Methoden für <xref:System.Net.WebRequest.GetResponse%2A> und <xref:System.Net.WebResponse.GetResponseStream%2A> zu verwenden.  
  
-   Die Anzahl der Verbindungen, die einer Internetressource geöffnet sind, kann erhebliche Auswirkungen auf Speichermenge und Durchsatz haben.  **System.Net** verwendet zwei Verbindungen pro Anwendung pro Host standardmäßig.  Das Festlegen der <xref:System.Net.ServicePoint.ConnectionLimit%2A>\-Eigenschaft in <xref:System.Net.ServicePoint> für die Anwendung kann diese Zahl für einen bestimmten Host erhöhen.  Das Festlegen der <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=fullName>\-Eigenschaft kann diese Standardeinstellung für alle Hosts erhöhen.  
  
-   Wenn SocketEbene Protokolle, Versuch geschrieben werden, um [TCPClient](frlrfsystemnetsocketstcpclientclasstopic) oder [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) zu verwenden, wann immer möglich anstelle des Schreibens direkt zu <xref:System.Net.Sockets.Socket>.  Diese Klassen mit zwei Clients kapseln die Erstellung von TCP und von UDP\-Sockets, ohne dass Sie veranlassen, die Details der Verbindung zu behandeln.  
  
-   Wenn Sie auf Sites zugreifen, die Anmeldeinformationen benötigen, verwenden Sie die <xref:System.Net.CredentialCache>\-Klasse, um einen Cache Anmeldeinformationen, anstatt sie mit jeder Anforderung angibt zu erstellen.  Die **CredentialCache**\-Klasse durchsucht den Cache, um die entsprechenden Anmeldeinformationen zu suchen, um mit einer Anforderung darzustellen und entlastet Sie von der Verantwortung des Erstellens und des Darstellens von Anmeldeinformationen auf Grundlage des URL.  
  
## Siehe auch  
 [Netzwerkprogrammierung in .NET Framework](../../../docs/framework/network-programming/index.md)